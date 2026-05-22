---
title: "Timestampi, qu'est-ce que c'est?"
description: "And all the King's horses  
             and all The King's men,  
             couldn't put Humpty  
             together again"
tags: ["firma", "e-firma", "timestamp", "tecnologia", "pki"]
draft: false
date: 2024-09-02
featured_image: "/images/stampel.png"
slug: "your-e-signature-is-broken"
---

**Las siguientes líneas cargan con dos o tres simplificaciones, porque entiendo que su extensión implican algo más que el discurso propio del derecho. Anoto que la e-sign está definida por sumas y por potenciaciones a números primos muy altos; basta saber eso para conocer la naturaleza de lo que elido.**

En términos simples, la firma electrónica usa algoritmos matemáticos complejos para garantizar la seguridad y la autenticidad del documento firmado, utilizando claves criptográficas que son únicas y prácticamente imposibles de falsificar. Este tipo de firma garantiza que el contenido no se ha modificado después de la firma, lo que le otorga un nivel de integridad bastante alto.

---

**Sobre el sello de tiempo y por qué importa**

Antes de avanzar, conviene detenerse en una pieza que suele pasarse por alto: el sello de tiempo (_timestamp_), emitido por lo que en el estándar RFC 3161 se denomina una _Time Stamping Authority_ (TSA).

Una TSA es una entidad externa de confianza —generalmente acreditada por una autoridad de certificación nacional o internacional— cuya única función es responder a una pregunta muy concreta: *¿existía este documento, con exactamente este contenido, en este momento?* Para responderla, el sistema que firma el documento le envía a la TSA una huella digital del mismo (un _hash_), y la TSA devuelve ese hash firmado junto con una marca de tiempo confiable, obtenida de fuentes atómicas o de servidores de tiempo de alta precisión. La TSA no necesita ver el contenido del documento; solo atestigua que ese hash —esa huella irreproducible— existía en ese instante.

El resultado es un testigo que no puede ser comprado ni persuadido: una cadena criptográfica que liga un documento a un momento, de manera independiente a cualquiera de las partes que lo firmaron.

Sin esta pieza, la firma electrónica queda coja. Sabe *quién* firmó y que el documento no fue alterado *después*, pero no puede probar *cuándo* ocurrió la firma con independencia del propio firmante. Y esa independencia es, precisamente, la que le da valor jurídico al acto.

---

**1. La firma electrónica da cuenta de la integridad del documento, de que el mismo no ha sido alterado una vez que fue firmado.**

La firma electrónica garantiza que el documento permanece intacto desde el momento en que se firma. Esta integridad es una de sus principales funciones, ya que asegura que no se ha hecho ningún tipo de modificación en el contenido después de la firma. Sin embargo, es importante señalar que la integridad no solo se refiere a que el documento no ha sido alterado, sino que también implica que el firmante es quien dice ser, gracias a la autenticación asociada con la firma.

**1.1. En este sentido es \~100% fiable. Error humano es aún posible pero no hablamos de eso.**

Aunque la firma electrónica es extremadamente confiable, siempre existe el riesgo de errores humanos. Por ejemplo, un firmante podría seleccionar el documento incorrecto para firmar o hacerlo de manera inapropiada. No obstante, en términos de la tecnología subyacente, la firma electrónica es casi infalible cuando se implementa correctamente, ya que se basa en criptografía avanzada que no puede ser alterada fácilmente sin la clave correspondiente.

---

**2. La voluntad expresada es connatural a la firma que refrenda tal voluntad.**

La firma electrónica refleja la voluntad del firmante en el momento de la firma, de la misma manera que lo haría una firma manuscrita. La firma electrónica no solo asegura la identidad del firmante, sino también su intención de vincularse al contenido del documento, lo que le da validez legal en muchos sistemas jurídicos.

**2.2. El transcurso del tiempo sucede por fuera del mismo y no depende de la voluntad de los firmantes o del firmante.**

El transcurso del tiempo es una variable externa que no está influenciada por las decisiones del firmante. Una vez que un documento es firmado electrónicamente, la hora y fecha en que se firma quedan registradas de forma precisa, sin que el firmante pueda alterar ese registro.

**2.2.3. El tiempo debe hacerse constar de una manera externa al mismo.**

Así que, va de suyo —como diría un Juez cuando sacará una conclusión dudosa— el tiempo en que se firma el documento debe registrarse de manera independiente del firmante, para asegurar que no pueda ser alterado. Esto generalmente se logra mediante un sello de tiempo proporcionado por una autoridad certificadora, que actúa como testigo confiable de la hora y fecha de la firma.

**2.2.3.4. Esta era la labor del Notario y esta era la labor del Secretario.**

Históricamente, el notario o el secretario judicial tenía la responsabilidad de garantizar la validez temporal de los actos jurídicos, dando fe de la fecha y la integridad de los documentos. Con la firma electrónica, este papel ha sido asumido por los sistemas automatizados de timestamping (sellado de tiempo), aunque el principio sigue siendo el mismo: proporcionar evidencia de que un documento fue firmado en un momento específico y que no ha sido alterado. El notario no era una formalidad: era la garantía de que ninguna de las partes podía regresar a reescribir la historia. La TSA debería ser, exactamente, eso.

---

**3. La fecha de la firma electrónica utilizada está fijada por el que la expide.**

Pero en nuestro caso la fecha en que se expide la firma electrónica es determinada por el sistema operativo del usuario que la emite. Esto puede ser una ventaja, ya que el proceso es automatizado y asegura que la fecha registrada sea precisa... o más o menos. Usualmente pasa por configurar el _locale_ de los Sistemas Operativos y señalar la hora correcta. O mejor, leer la fecha desde un servidor, por ejemplo: ntp.intn.gov.py.

**3.3. El que la expide puede equivocarse o mentir.**

Aunque los sistemas de firma electrónica son generalmente confiables, siempre existe la posibilidad de que el emisor cometa un error o incluso actúe de mala fe, alterando la fecha o la información del documento. Sin embargo, la mayoría de los sistemas de firma electrónica están diseñados para minimizar este tipo de riesgos mediante registros verificables e inmutables.

Pero "diseñados para minimizar" no es lo mismo que "inmunes por diseño". Cambiar la hora del sistema operativo antes de firmar un documento es, en la mayoría de los entornos de escritorio, una operación de usuario estándar. No requiere conocimientos técnicos avanzados ni herramientas especiales. Requiere acceso al panel de configuración y la intención de hacerlo. Eso es todo. El sistema no tiene cómo distinguir si la hora que lee el reloj del cliente refleja la realidad o una realidad conveniente. La firma quedará sellada con esa hora, y será, formalmente, válida.

Este no es un problema de implementación descuidada: es un problema de arquitectura. Si la fuente de la hora es local, la fuente de la hora es controlable. Y si es controlable, no puede ser confiable.

**3.3.1. Es natural que ante una disonancia entre una y otra valdrá la fecha puesta por el Judisoft.**

Ante la posible discrepancia entre la fecha registrada por el software utilizado (Judisoft) y la real en que se firmó el documento, esto podría generar incertidumbre si no se cuenta con un sello de tiempo independiente que valide la firma.

**3.3.1.2. El Judisoft decide la fecha por sí mismo.**

Y ahí está el nudo. El sistema que registra el acto jurídico también decide cuándo ocurrió. No hay un árbitro externo. No hay una TSA que certifique el hash antes de que la firma se complete. El Judisoft es, al mismo tiempo, la parte y el testigo. Eso no es un detalle técnico menor: es una contradicción en los términos de cualquier sistema de fe pública.

---

**4. La firma electrónica de la forma en que se la ha concebido e impuesta en el medio, está rota. No vale, ni sirve a sus fines.**

La firma electrónica tal como se ha implementado actualmente no cumple con su propósito original. El sistema, en muchos casos, no es lo suficientemente robusto para garantizar la seguridad y la validez temporal de los documentos, debido a fallos en la infraestructura del timestamping o en la gestión de la fecha.

Decir que está "rota" no es retórica. Es una descripción técnica precisa. Un sistema de firma sin timestamping externo acreditado puede probar *qué* se firmó y *quién* lo firmó, pero no puede probar *cuándo*. Y en el derecho, el cuándo no es un dato auxiliar: es, con frecuencia, el dato que define si un plazo venció, si una obligación nació, si una responsabilidad se activó. Retirar esa garantía del sistema y reemplazarla por la hora del reloj del cliente es como pedirle al acusado que certifique su coartada.

---

**¿Qué ocurre si una firma no lleva sello de tiempo?**

Como se menciona, el sello de tiempo no solo asegura que el documento no ha sido alterado desde que se firmó, sino que también proporciona una prueba independiente de que la firma fue efectuada en un momento determinado. Sin este sello, sería mucho más difícil probar que un documento no fue modificado después de su firma, lo que podría generar disputas legales costosas.

**El sellado de tiempo es esencialmente un testigo independiente. Proporciona las pruebas necesarias para demostrar que el documento no ha cambiado desde que se envió el hash del documento a la TSA en el momento de la firma.**

El sello de tiempo actúa como un testigo confiable que no solo valida la fecha y hora de la firma, sino que también certifica que el documento ha permanecido inalterado desde su firma, lo que lo convierte en una herramienta clave para la integridad legal del documento.

---

**¿Qué debería cambiar?**

La solución no es compleja. Es, de hecho, más sencilla que el problema que genera su ausencia.

Primero: integrar una TSA acreditada al flujo de firma. Antes de que la firma se complete y se registre, el sistema debería enviar el hash del documento a una TSA externa —que podría ser operada por la propia autoridad certificadora del Estado, o por una entidad internacional reconocida— y esperar la respuesta sellada. Ese sello pasa a ser parte inseparable del documento firmado.

Segundo: que la TSA lea su hora de una fuente atómica o de un servidor de tiempo público y verificable, no del reloj de ninguna de las partes. El INTN, a través de ntp.intn.gov.py, ya ofrece una referencia horaria nacional. Esa infraestructura existe. El problema no es de recursos: es de voluntad de integración.

Tercero: que el sistema registrador —el Judisoft u otro equivalente— no acepte una firma sin sello de tiempo válido. Que la validación sea parte del proceso, no una opción. Del mismo modo en que un notario no puede dar fe de un acto que no presenció, el sistema no debería registrar una firma que no puede probar cuándo ocurrió.

Nada de esto requiere reinventar la rueda. El estándar RFC 3161 tiene más de veinte años. Las TSA públicas y privadas existen en toda la región. Lo que falta no es tecnología: es la decisión de usarla correctamente.

---

Humpty Dumpty cayó del muro. No porque la pared fuera débil, sino porque nadie había diseñado una red de contención. Todos los caballos y todos los hombres del Rey llegaron después. En infraestructura jurídica digital, como en muchas otras cosas, el momento de construir la red es antes de la caída, no durante.

