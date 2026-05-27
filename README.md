
# Java+Javalin e recursos OOP
## Parte 1
exemplo PoiService:

```java
app.get("/poi", ctx -> ctx.json(new Poi("Restaurante Universitário 2", -29.71400, -53.71937)));
app.get("/poilist", ctx -> ctx.json(POIS));
app.get("/near/{lat}/{lon}", ctx -> {
  double givenLat = Double.parseDouble(ctx.pathParam("lat"));
  double givenLon = Double.parseDouble(ctx.pathParam("lon"));
  double nearKm = 1.5;
  List<Poi> near = new ArrayList<>();
  for (var p : POIS) if (distanceKm(givenLat, givenLon, p.latitude, p.longitude) <= nearKm) near.add(p);
  ctx.json(near);
});
```

https://github.com/user-attachments/assets/6ba25a75-99d1-4409-b375-8061c68d31bd


## Parte 2

### Exemplos
### Recursos conhecidos
- ArrayList<>()
- new
- construtores
- `this.` em public User(Integer id, String n, String e) { this.userId = id; this.name = n; this.email = e; }
- Overloading

### Recursos desconhecidos
- `record` em public record Poi(String poi, double latitude, double longitude) {}
- private/public static
- throws Exception/SQLException
- `final` em private static final List<String> ADVICES = List.of()

### Serviço gerado
https://github.com/user-attachments/assets/36940b8f-a538-4e82-8296-58564f4fc18f

### Recursos conhecidos
- Override(Employee.java)
- toString (Employee.java)
### Recursos desconhecidos
- tipos parametrizados ⁵
- final class ⁶

## Referências

1. [Java Records (JLS §8.10)](https://docs.oracle.com/javase/specs/jls/se21/html/jls-8.html#jls-8.10) — Oracle, Java Language Specification.
2. [Class Members (`static`)](https://docs.oracle.com/javase/tutorial/java/javaOO/classvars.html) — The Java Tutorials, Oracle.
3. [Declaring Exceptions (`throws`)](https://docs.oracle.com/javase/tutorial/essential/exceptions/declaring.html) — The Java Tutorials, Oracle.
4. [Final Variables (JLS §4.12.4)](https://docs.oracle.com/javase/specs/jls/se21/html/jls-4.html#jls-4.12.4) — Oracle, Java Language Specification.
5. [Generic Types](https://docs.oracle.com/javase/tutorial/java/generics/types.html) — The Java Tutorials, Oracle.
6. [Final Classes and Methods](https://docs.oracle.com/javase/tutorial/java/IandI/final.html) — The Java Tutorials, Oracle.


