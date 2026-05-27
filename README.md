
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

### Recursos desconhecidos
