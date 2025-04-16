# 🛠️ Spring Boot - Gestion de Produits

Ce projet est une application simple de gestion de produits réalisée avec **Spring Boot**, **Spring Data JPA**, **Lombok** et **H2 Database et aussi MYSQL**.

---

## 📦 Technologies utilisées

- Java 17+
- Spring Boot
- Spring Data JPA
- H2 Database
- Lombok
- Maven
- IntelliJ IDEA Ultimate

---

## ⚙️ Étapes de mise en place

### ✅ 1. Créer un projet Spring Initializer

Dépendances à inclure :
- Spring Web
- Spring Data JPA
- H2 Database
- Lombok

---

### ✅ 2. Configuration de Lombok dans `pom.xml`

```xml
<dependency>
    <groupId>org.projectlombok</groupId>
    <artifactId>lombok</artifactId>
    <version>1.18.34</version>
    <scope>provided</scope>
</dependency>

<build>
    <plugins>
        <plugin>
            <groupId>org.projectlombok</groupId>
            <artifactId>lombok</artifactId>
            <version>1.18.34</version>
        </plugin>
    </plugins>
</build>

```
✅ 3. Créer l'entité Product
```
import jakarta.persistence.*;
import lombok.*;

@Entity
@Data
@NoArgsConstructor
@AllArgsConstructor
public class Product {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    private String name;
    private double price;
    private int quantity;
}
```
✅ 4. Créer l'interface ProductRepository

```
import org.springframework.data.jpa.repository.JpaRepository;

public interface ProductRepository extends JpaRepository<Product, Long> {
}
```
✅ 5. Configurer application.properties

```
spring.datasource.url=jdbc:h2:mem:testdb
spring.datasource.driver-class-name=org.h2.Driver
spring.datasource.username=sa
spring.datasource.password=
spring.jpa.database-platform=org.hibernate.dialect.H2Dialect
spring.jpa.hibernate.ddl-auto=update
spring.h2.console.enabled=true
```

🧪 Fonctionnalités à tester

➕ Ajouter un produit

📃 Consulter tous les produits

🔍 Consulter un produit par ID

🔎 Rechercher des produits (par nom par exemple)

✏️ Mettre à jour un produit

❌ Supprimer un produit
```
```
AUTEUR : SALAHEDDINE BACHA
--------------------------

