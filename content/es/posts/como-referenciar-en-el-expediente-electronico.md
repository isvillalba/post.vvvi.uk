---
title: "¿Cómo referenciar en el expediente electrónico?"
description: "El problema de nombrar lo que ya no tiene fojas"
tags: ["e-expediente", "fojas", "judisoft", "qr", "almacenamiento"]
date: 2024-03-10
slug: "como-referenciar-en-el-expediente-electronico"
---

## El problema de las fojas

Nombrar algo con precisión es el primer paso para poder actuar sobre ello. Y ese nombre tiene un requisito fundamental: debe ser único, para que nadie lo confunda con otra cosa. Odiseo lo entendió cuando, en la cueva de Polifemo, se hizo llamar «Nadie». Gracias a esa astucia nominal, cuando Polifemo grita que «Nadie» lo ha cegado, ninguno de sus vecinos acude en su auxilio. La identidad, o su ausencia, tiene consecuencias prácticas.

En el proceso judicial tradicional, la fórmula para nombrar una pieza del expediente era simple y eficaz:

> *a fojas x de los autos* / *desde fojas x a fojas y*

Hoy, en el expediente electrónico, esas fojas ya no existen. Sin embargo, la necesidad de referenciar con precisión subsiste intacta. Los juzgados, en ocasiones, resuelven el problema con providencias del tipo *«estése a lo dispuesto»* sin indicar a cuál de los diez escritos anteriores se refieren,[^1] lo que obliga a interponer aclaratorias que podrían haberse evitado con una referencia mínimamente precisa.

[^1]: Las providencias de tipo *«estése»* que no indican el objeto concreto de lo que se ordena son nulas de toda información y, en la práctica, siempre deben ser recurridas en aclaratoria.

Una solución habitual consiste en citar la fecha y el título del escrito. En la mayoría de los casos, esto es suficiente. El inconveniente aparece cuando dos escritos de similar naturaleza se presentan el mismo día con horas distintas —y, en algunos casos, con QR idénticos—. La coincidencia no es frecuente, pero ocurre, y cuando ocurre, la ambigüedad es total.

## El número de documento como referencia principal

En condiciones normales, el Judisoft asigna a cada presentación un nombre de archivo con un número entero único: `n.pdf`. Ese número es, en la práctica, el identificador más confiable de cada pieza del expediente electrónico.

Una referencia bien construida podría adoptar la siguiente forma:

> *el escrito de nulidad presentado por la demandada el día 27 del corriente bajo el documento **34343.pdf***

Esta construcción combina tres datos: la naturaleza del escrito (qué es), la parte que lo presentó y la fecha (cuándo fue), y el identificador de archivo (cuál es, sin posibilidad de confusión). No es necesario citar los tres elementos siempre, pero la inclusión del número de archivo elimina toda ambigüedad residual.

## El problema de los enlaces internos

Los enlaces que genera el Judisoft para acceder a los documentos son internos al sistema: solo son accesibles para un usuario autenticado. Eso los hace inútiles como referencia externa —por ejemplo, para incluir en un escrito que leerá un colega, un perito o un tribunal de alzada sin acceso directo al expediente.

La solución, entonces, pasa por disponer de una copia propia del documento en un servidor accesible públicamente. Esto, por otra parte, es una práctica recomendable con independencia del sistema judicial: ningún servicio de almacenamiento —por sólido que parezca— está exento del riesgo de pérdida de datos. Conservar una copia propia es una medida elemental de gestión documental.

Con una copia disponible en línea, la referencia podría completarse así:

> *…cuya copia obra en* `https://el-dominio-del-estudio.com/casos/34343.pdf`

## Opciones de almacenamiento

El mercado actual ofrece varias alternativas según el nivel de conocimiento técnico disponible y el volumen de documentos a gestionar.

### Almacenamiento en la nube convencional

Para la mayoría de los estudios jurídicos, los servicios de nube convencional son la opción más práctica. Entre las alternativas actuales más relevantes:

- **Google Drive**: 15 GB gratuitos con cuenta Google; integración nativa con el ecosistema de documentos de Google. Permite compartir archivos mediante enlaces públicos o restringidos.
- **Dropbox**: Pionero en sincronización de archivos, con planes profesionales que incluyen hasta 2 TB. Ampliamente integrado con aplicaciones de terceros.
- **MEGA**: Ofrece 20 GB gratuitos con cifrado de extremo a extremo. Es una opción atractiva para quienes priorizan la confidencialidad de la información, lo cual es relevante en el ámbito jurídico.
- **OneDrive**: Especialmente conveniente para quienes ya utilizan el ecosistema Microsoft 365, que incluye las aplicaciones de Office. El almacenamiento se integra directamente con el escritorio de Windows.
- **pCloud**: Destaca por sus planes de pago único (sin suscripción mensual) y por sus sólidas opciones de cifrado. Dispone de planes desde 10 GB gratuitos.

En todos estos casos, el flujo de trabajo es sencillo: se sube el documento al servicio, se genera un enlace público y ese enlace se incorpora a la referencia.

### Almacenamiento descentralizado mediante IPFS

El **IPFS** (InterPlanetary File System, Sistema de Archivos Interplanetario) es un protocolo descentralizado de almacenamiento y distribución de archivos. A diferencia de los servicios convencionales, que dependen de un servidor central, IPFS distribuye los archivos en una red de nodos independientes. Cada archivo recibe un identificador único basado en su contenido —llamado CID (*Content Identifier*)—, lo que garantiza que el archivo no puede ser modificado sin que el identificador cambie. Esto tiene una consecuencia práctica relevante para el ámbito forense: la autenticidad del documento puede verificarse criptográficamente.

Para usar IPFS sin necesidad de gestionar infraestructura propia, existen servicios de *pinning* —que mantienen los archivos disponibles en la red— con planes gratuitos suficientes para el uso profesional individual:

- **Pinata** ([pinata.cloud](https://pinata.cloud)): Es actualmente el servicio de pinning IPFS más accesible para usuarios no técnicos. Ofrece una interfaz web intuitiva, una API robusta para desarrolladores, y un plan gratuito con capacidad limitada pero funcional para volúmenes pequeños. Los archivos se suben a través del panel web y quedan disponibles con una URL pública estable.
- **Filebase** ([filebase.com](https://filebase.com)): Compatible con el protocolo S3 de Amazon, lo que facilita su integración con otras herramientas. Ofrece almacenamiento geo-redundante con replicación automática en múltiples nodos.

Una referencia con IPFS se vería así:

> *…cuya copia obra en* `https://gateway.pinata.cloud/ipfs/QmXyZ...`

La principal ventaja de IPFS frente a los servicios convencionales es que el enlace está vinculado al contenido, no a una ubicación. Si el archivo no ha sido alterado, el CID lo confirma. La desventaja es que requiere un servicio de pinning activo para garantizar disponibilidad, y la curva de aprendizaje, aunque baja con Pinata, existe.

### Hosting web tradicional

Para quienes ya disponen de un sitio web propio —o están dispuestos a contratar uno—, el almacenamiento de documentos en un servidor web es la solución más directa. Un plan de hosting compartido con dominio propio permite alojar documentos bajo una URL del tipo `https://estudio-juridico.com/expedientes/34343.pdf`.

Esta opción combina control total sobre la nomenclatura y la organización de los archivos con la posibilidad de construir una presencia en línea para el estudio. Los planes básicos de hosting compartido con dominio propio rondan los 3 a 8 USD mensuales dependiendo del proveedor y la región.

## El número al pie del documento y el hash de presentación

Al final de cada escrito presentado en el Judisoft aparece una cadena de caracteres hexadecimales. Aunque su origen técnico preciso no está documentado públicamente, todo indica que se trata de un **hash** —una huella digital criptográfica— vinculado a la presentación. Un hash es una función matemática que transforma un conjunto de datos en una cadena de longitud fija; la misma entrada produce siempre el mismo resultado, y cualquier modificación mínima del documento produce un hash completamente diferente.[^2]

[^2]: Para una introducción accesible a las funciones hash, véase: Cáceres-Gutiérrez, Á. et al., «Funciones hash criptográficas», disponible en la Facultad de Ciencias de la Universidad de Málaga.

Este hash, junto con el enlace de validación que genera el sistema, permite verificar que el documento presentado coincide con el que obra en el expediente, y puede funcionar como un elemento adicional de referencia para acreditar la autenticidad de una copia.

> **Nota importante**: el enlace de validación no debe ser utilizado repetidamente desde equipos externos. El servidor del Judisoft lo interpreta como un intento de acceso automatizado y puede bloquear la IP del solicitante.

## El QR al final del documento

Al lado del hash, los documentos del Judisoft incluyen un código QR. La legibilidad de ese QR es, en algunos casos, deficiente. Si la dificultad de lectura fuera intencional, indicaría que el dato contenido en él no está destinado a ser accedido fácilmente por el usuario, lo cual plantea preguntas sobre su función y sobre la política de transparencia del sistema. Si es un problema técnico, debería ser reportado y corregido. En cualquier caso, los datos que contiene merecen ser conocidos, y quien tenga acceso a ellos y desee compartirlos puede hacerlo a través de los comentarios.

---

En síntesis: la referencia más precisa en el expediente electrónico combina el número de archivo asignado por el Judisoft con una copia del documento disponible en línea bajo una URL estable. El método de almacenamiento —nube convencional, IPFS o hosting propio— dependerá del volumen documental, el presupuesto disponible y el nivel de familiaridad con cada herramienta. Lo que no cambia es la necesidad de nombrar con precisión: sin una referencia inequívoca, el escrito existe, pero nadie sabe de cuál se habla.
