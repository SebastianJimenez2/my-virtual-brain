The detection algorithms become complicated by the dynamic aspects which are not directly capturable in metrics. So, an alternative to algorithmic detection methods are logic-based approaches, which have demonstrated capabilities to quickly define and execute complex queries over code bases.
 > Difficulty: Antipattern definitions are usually given as textual descriptions.
 
**¿Cómo lo hace?**
 1. Conoce el patrón a analizar, su estructura tanto en diseño como en código
 2. Hace clases verificadoras, en donde deben constar las instancias, asociaciones, herencias, etc. de un patrón bien implementadas, generalmente usa getters (se verifica la estructura y comportamiento de patrones y anti-patrones).
 3. Se pone a prueba el código y las clases verificadoras analizan que todo esté como debería estar implementado según el paso 1.

(6/10 solo detecta anti-patrones en base a patrones de diseño)


 
 