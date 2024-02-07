PARCIAL 2022 JAVA
![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/f419a1f0-540e-45e3-9cfa-d36e1309076f/Untitled.png)
Diagrama UML:
![Diagram 2024-02-05 22-06-17.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/dd893beb-7801-45ce-b05f-4d2d64bf0089/c534191d-b593-4fa3-8d5e-63590fe784a1/Diagram_2024-02-05_22-06-17.png)
UML FINAL
![UML.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/dd893beb-7801-45ce-b05f-4d2d64bf0089/6adcf639-237e-4faf-9e48-f6243a0a91a5/UML.png)
### La clase `Area` la estoy definiendo como abstracta por las siguientes razones:

1. **No se espera instanciar objetos de la clase Area directamente**: `Area` representa un concepto genérico de área, pero en el problema siempre vamos a necesitar áreas de un tipo específico (gélida, tundra, etc.). Entonces no tiene sentido crear instancias de `Area`, solo de sus subclases concretas.
2. **Define comportamiento común a través de la interfaz AreaEnPeligro**: Al implementar la interfaz `AreaEnPeligro`, se establece que todas las clases de áreas ahora deben definir el método `enPeligro()`. Esto permite definir una "plantilla" de comportamiento común (determinar si el área está en peligro), donde cada subclase implementa la lógica particular.
3. **Permite trabajar polimórficamente con las subclases**: Al tener una referencia de tipo `Area` se pueden manejar en forma conjunta instancias de `AreaGelida`, `AreaTundra`, etc. Esto simplifica el código que las utiliza.
4. **Favorece el principio de sustitución de Liskov**: las subclases son siempre un "tipo de" la superclase. Cualquier subclase puede sustituir a una instancia de `Area` sin afectar el funcionamiento del sistema.

### Ventaja de usar una interface para el método abstracto

- Se aplica el principio de programación a interfaces, se desacopla la interfaz de la implementación y se permite polimorfismo.
- La ventaja es que si en un futuro se necesitan clases que no hereden de `Area` pero si necesiten implementar `enPeligro()`, se puede hacer implementando la interface `AreaEnPeligro`.
