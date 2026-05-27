
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
- `record` em `public record Poi(String poi, double latitude, double longitude) {}` - classe imutável compacta que gera automaticamente construtor, getters, `equals`, `hashCode` e `toString`.  ¹
- `private`/`public static` - modificadores que controlam visibilidade (`private`/`public`) e indicam que o membro pertence à classe, não à instância (`static`). ²
- `throws Exception`/`SQLException` - cláusula que declara as exceções checadas que um método pode propagar para quem o chamou. ³ 
- `final` em `private static final List<String> ADVICES = List.of()` ⁴ - torna a variável uma constante: só pode ser atribuída uma única vez. ⁴

### Serviço gerado

### Recursos conhecidos
- Override(Employee.java)
- toString (Employee.java)
### Recursos desconhecidos
- tipos parametrizados - classes/interfaces que recebem um tipo como argumento (ex.: `List<Employee>`), garantindo segurança de tipos em tempo de compilação. ⁵
- `final class` - classe marcada como `final` não pode ser estendida (proíbe herança). ⁶

## Referências

1. [Java Records (JLS §8.10)](https://docs.oracle.com/javase/specs/jls/se21/html/jls-8.html#jls-8.10) — Oracle, Java Language Specification.
2. [Class Members (`static`)](https://docs.oracle.com/javase/tutorial/java/javaOO/classvars.html) — The Java Tutorials, Oracle.
3. [Declaring Exceptions (`throws`)](https://docs.oracle.com/javase/tutorial/essential/exceptions/declaring.html) — The Java Tutorials, Oracle.
4. [Final Variables (JLS §4.12.4)](https://docs.oracle.com/javase/specs/jls/se21/html/jls-4.html#jls-4.12.4) — Oracle, Java Language Specification.
5. [Generic Types](https://docs.oracle.com/javase/tutorial/java/generics/types.html) — The Java Tutorials, Oracle.
6. [Final Classes and Methods](https://docs.oracle.com/javase/tutorial/java/IandI/final.html) — The Java Tutorials, Oracle.


