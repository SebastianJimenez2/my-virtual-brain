Code Smells es un síntoma de un antipattern.

**¿Cómo lo hacen?**
1. Analizador de métricas. Extrae métricas basadas en el código fuente (se usa para dos de los 3 antipatrones que detecta el programa: Blob and Swiss Army Knife) (CK metrics con umbrales sacados de forma empírica y mediante exploración de proyectos)
2. Analizador de código estático que analiza (valga la redundancia) acorde ciertas reglas, extracción de código y trata de darle un significado (lava flow)
3. Mediante esta información se filtra y se trata de entender el estilo de código del programador considerando el tamaño del proyecto para evitar condiciones no deseada como marcar una clase como antipatrón por un ==estilo de codificación.== La intervención de esta filtración es ==manual.==
### Six problems in antipattern detection processes 
- **Problem 1:** Making a decision that a class exists as an antipattern or not, may be an uncertain operation. Because a class which shows all symptoms of an antipattern may be a regular class. Thus analyst opinion is needed in this process to determine  antipatterns more accurately.
- **Problem 2:** Listing large set of candidate classes can be an inefficient process. ResuIts may have too many false positives thus detection technique may be discarded. Assessments of an analysts are needed to produce a list of candidates.
- **Problem 3:** Considering the assessments of analysts is a complex process. A design or class which is interpreted strong, regular or poor by analyst depends on knowledge, experience and background of analyst.
- **Problem 4:** Detection framework needs to be considered while detecting antipatterns. Classes which are specified "good" by most of quality analysts may violate some design concepts in a specific environment.
- **Problem 5:** Determining thresholds is a significant process in antipattern detection. Different threshold values may be interpreted differently by quality analysts.
- **Problem 6:** Improving and using semantic data are problematic operations. Some antipattern symptoms include semantic data and an automated detection technique is required to consider them.