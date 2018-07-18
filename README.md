# jenkins

Первый абзац
***
Второй абзац

Первый абзац
---
Второй абзац

h1 заголовок первого уровня
=====================
h2 заголовок второго уровня
-----------------------------------
### h3 заголовок третьего уровня
#### h4 заголовок четвёртого уровня
##### h5 заголовок пятого уровня
###### h6 заголовок шестого уровня

[Мой сайт](http://webdesign.ru.net)

<http://webdesign.ru.net>

**Жирный шрифт**
***Наклонный жирный***

`выделенные слова`

    dir /fonts
    dir /images
    dir /js
    
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```
```scss /* или css */
@import "bower_components/tree-normalize/generic.normalize";
h1 {
 font-size:1.5em;
 font-weight: 300;
}
```

```java
public static void main(String[] args)
```

> Текст
> 
> Продолжение текста выделенного блока
> Завершение текста
>> цитата второго уровня
>>> цитата 3 уровня

Название файла  | Содержание файла
----------------|----------------------
style.css       | Пустой файл каскадной таблицы стилей, в который производится сбока необходимых стилей
reset.css       | Reset CSS от Эрика Мейера
normalize.css   | Нормалайзер CSS от Nicolas Gallagher
block.css       | Основные стили блоков системы
addition.css    | Дополнительные стили
fontawesome.css | Стили иконочного шрифта
layout.css      | Основные стили, применительно к определённому сайту
lightbox.css    | Стили лайтбокса, если таковой используется
index.html      | Индексный файл для проверки вносимых изменений

* Пункт 1
* Пункт 2
* Пункт 3

1. Пункт 1
2. Пункт 2
3. Пункт 3

_наклонный_ _шрифт_ _наклонный__шрифт_

![screenshot of sample](http://webdesign.ru.net/images/Heydon_min.jpg)
`Комбинируя эти маркеры вы сможете правильно разметить свой текст, сделать его более понятным.
Надеюсь, что эта статья будет вам полезна. Успехов в работе на GitHub!`

#in pom.xml
------------------------
```xml
<dependency>
    <groupId>org.postgresql</groupId>
    <artifactId>postgresql</artifactId>
</dependency>

<dependency>
    <groupId>org.liquibase</groupId>
    <artifactId>liquibase-core</artifactId>
</dependency>

			<plugin>
                <groupId>org.liquibase</groupId>
                <artifactId>liquibase-maven-plugin</artifactId>
                <version>3.6.2</version>
                <configuration>
                    <propertyFile>src/main/resources/liquibase.properties</propertyFile>
                </configuration>
                <executions>
                    <execution>
                        <goals>
                            <goal>update</goal>
                        </goals>
                    </execution>
                </executions>
            </plugin>
```

#in resources
`resources/liquibase.properties` 
```properties
driver=org.postgresql.Driver
url=jdbc:postgresql://localhost:5432/postgres
username=postgres
password=admin
changeLogFile=src/main/resources/db-migration/master.xml
```

`resources/db-migration/master.xml`

```xml
<databaseChangeLog xmlns="http://www.liquibase.org/xml/ns/dbchangelog"
                   xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
                   xsi:schemaLocation="http://www.liquibase.org/xml/ns/dbchangelog
                   http://www.liquibase.org/xml/ns/dbchangelog/dbchangelog-3.5.xsd">

    <changeSet author="Marat_Taimagambetov" id="1456796982209-1">
        <createTable tableName="customer">
            <column autoIncrement="true" name="id" type="BIGINT">
                <constraints primaryKey="true"/>
            </column>
            <column name="balance" type="INT">
                <constraints nullable="false"/>
            </column>
            <column name="email" type="VARCHAR(255)">
                <constraints nullable="false"/>
            </column>
            <column name="name" type="VARCHAR(50)">
                <constraints nullable="false"/>
            </column>
            <column name="version" type="BIGINT"/>
        </createTable>
    </changeSet>

</databaseChangeLog>
```
