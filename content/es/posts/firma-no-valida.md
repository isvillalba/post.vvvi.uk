---
title: "No valida la firma"
description: "Por qué algunos documentos firmados digitalmente aparecen como inválidos y qué significa realmente esa advertencia."
tags: ["firma digital", "certificados", "PKI", "SSL", "documentos electrónicos"]
draft: false
date: 2025-04-15
slug: "no-valida-la-firma-digital"
---

La escena suele repetirse: un oficio firmado digitalmente llega correctamente al destinatario, pero el sistema muestra una advertencia indicando que la firma “no es válida” o que no puede verificarse.

En la práctica, muchas veces el documento sí fue firmado correctamente. El problema no necesariamente está en la firma, sino en la infraestructura de confianza que debería permitir verificarla automáticamente.

Ese detalle técnico, que durante años pasó relativamente desapercibido dentro de ciertos circuitos institucionales, empieza a hacerse visible cuando los documentos deben circular entre organismos distintos, sistemas distintos y criterios técnicos distintos.

Y ahí aparece el verdadero problema: la diferencia entre que una firma exista y que una firma pueda validarse.

## “No veo la validación en mi pantalla”

Quienes trabajamos con oficios electrónicos probablemente nos encontramos más de una vez con documentos firmados digitalmente que, al abrirse en una computadora institucional, aparecen como “firma no válida” o directamente sin validación visible.

Mientras los intercambios ocurrían exclusivamente dentro del Poder Judicial, esto terminaba funcionando como una convención informal: sabíamos que el documento provenía de quien decía provenir, aunque el software no pudiera verificarlo correctamente.

El problema aparece cuando esos documentos deben circular hacia otras instituciones del Estado o hacia organismos externos que sí esperan una validación técnica completa de la firma digital. En esos casos, la advertencia deja de ser una curiosidad y pasa a convertirse en un obstáculo operativo.

Algunos juzgados incluso terminaron recurriendo nuevamente al papel para ciertos trámites. No porque la firma digital no exista, sino porque la infraestructura alrededor de ella está incompleta.

## ¿Qué significa realmente que una firma “valide”?

Existe una confusión bastante común: pensar que el mensaje “firma válida” significa simplemente que alguien firmó el documento.

En realidad, el software está haciendo varias verificaciones simultáneas. La firma digital moderna no funciona únicamente como una imagen o una marca de autoría; funciona como un mecanismo criptográfico que intenta responder varias preguntas al mismo tiempo:

- ¿el documento fue alterado después de firmado?;
- ¿quién lo firmó?;
- ¿ese certificado era confiable?;
- ¿la firma seguía siendo válida en ese momento?;
- ¿la cadena de confianza está completa?

Cuando una de esas verificaciones falla, muchos programas muestran directamente “firma inválida”, aunque el documento siga siendo perfectamente legible y aunque la firma criptográfica siga existiendo.

Cuando un programa informa que una firma digital es válida, en realidad está verificando varias cosas al mismo tiempo.

La más importante es la integridad del documento: que el contenido no haya sido alterado desde el momento de la firma. Es decir, que el documento actual coincida exactamente con el que fue firmado originalmente.

Pero además el sistema intenta verificar:

- la autenticidad del certificado utilizado;
- la cadena de confianza de ese certificado;
- y, en algunos casos, la validez temporal de la firma.

Ese último punto suele depender de servicios de sellado de tiempo o de infraestructura adicional que muchos sistemas todavía implementan de manera incompleta, aun cuando técnicamente no sea complejo hacerlo.

## El problema de la cadena de certificados

Acá es donde normalmente aparece el conflicto real.

La mayoría de los sistemas de firma no confían automáticamente en cualquier certificado. Necesitan reconstruir una cadena de validación que conecte el certificado del firmante con una autoridad reconocida.

Es parecido a una cadena de referencias:

> “Yo confío en esta autoridad; esta autoridad confía en este certificado; por lo tanto, puedo confiar en quien firmó”.

Si alguno de esos pasos falta, la validación falla.

Y eso no significa necesariamente que el documento sea falso. Significa, simplemente, que el software no puede demostrar automáticamente toda la cadena de confianza.

La mayoría de los errores de validación no se producen porque la firma esté “mal hecha”, sino porque el certificado utilizado no incluye una cadena de confianza completa.

En términos simples: el software necesita poder reconstruir quién firmó el documento y quién certificó a quien firmó, hasta llegar a una autoridad reconocida.

Ese modelo es el mismo que se utiliza en SSL/TLS para conexiones HTTPS. No alcanza con tener un certificado; además debe existir una cadena verificable que permita confiar en él.

En algunos documentos institucionales ocurre justamente eso: el certificado del firmante existe, pero la cadena aparece incompleta. Por eso ciertos programas muestran advertencias o directamente indican que la firma no puede validarse.

## Un esquema extremadamente centralizado

Toda esta infraestructura pertenece al mundo de la PKI (*Public Key Infrastructure*), que es la misma lógica utilizada para HTTPS, SSL/TLS y buena parte de la seguridad moderna en Internet.

El problema es que la documentación técnica suele explicar el funcionamiento criptográfico, pero rara vez explica bien el aspecto institucional del sistema: quién confía en quién y por qué.

Porque, al final del día, las firmas digitales no son solamente matemática. También son acuerdos de confianza.

Simplificando muchísimo, el modelo dominante funciona así:

1. una autoridad certificadora emite certificados;
2. los sistemas operativos y programas deciden confiar en esa autoridad;
3. los certificados emitidos por ella heredan esa confianza;
4. y las firmas realizadas con esos certificados pasan a considerarse verificables.

Es un modelo extremadamente centralizado, aunque muchas veces se lo presente únicamente como una cuestión técnica.

La infraestructura de certificados digitales suele resultar difícil de entender al principio. Gran parte de la documentación técnica asume conocimientos previos y, aun después de leer bastante sobre SSL o PKI, no siempre queda claro cómo encajan todas las piezas.

Simplificando mucho, el sistema funciona como una cadena de confianza centralizada:

1. una autoridad certificadora emite certificados;
2. esos certificados identifican a personas o sistemas;
3. y las firmas digitales se apoyan en esa confianza preexistente.

No es el único modelo posible, pero es el que terminó predominando en la práctica.

![](/grafico.svg)

Este artículo continuará en futuras partes porque el diagrama, por sí solo, probablemente no alcance para explicar todas las implicancias del sistema.

## ¿Puede una institución emitir certificados?

Sí. Técnicamente, cualquier institución puede hacerlo.

Una Corte Suprema, una universidad, una empresa o incluso una persona podrían emitir certificados digitales y construir su propio esquema de validación.

La diferencia está en otra parte: si terceros aceptan o no esa autoridad como confiable.

Por eso muchas discusiones sobre firma digital parecen técnicas, pero en realidad son institucionales. El verdadero problema no es quién puede firmar, sino quién tiene capacidad de imponer confianza sobre otros sistemas.

En términos prácticos, la criptografía resuelve el problema de integridad; la infraestructura institucional intenta resolver el problema de confianza.

Una duda razonable es si una institución como la Corte Suprema puede emitir certificados digitales aun cuando no sea una autoridad certificadora reconocida formalmente.

La respuesta corta es sí.

Cualquier entidad puede emitir certificados y establecer un esquema de validación propio. La diferencia no está en la posibilidad técnica de hacerlo, sino en el nivel de reconocimiento jurídico y confianza que terceros estén dispuestos a otorgarle.

En otras palabras: el problema no es la existencia del certificado, sino quién confía en él y bajo qué condiciones.

## Certificadores autorizados y no autorizados

A veces se habla de los “certificadores no autorizados” como si sus certificados fueran automáticamente inválidos. Pero técnicamente no es así.

Un certificado emitido por una autoridad no reconocida oficialmente puede seguir siendo criptográficamente correcto y funcional. Incluso puede ofrecer niveles de seguridad equivalentes.

La diferencia suele ser jurídica y probatoria.

Los certificados emitidos por autoridades oficialmente reconocidas tienen, en muchos sistemas legales, presunciones normativas especiales: se presume autenticidad, integridad o autoría salvo prueba en contrario.

En cambio, las firmas emitidas fuera de ese esquema pueden requerir demostraciones adicionales.

Pero eso no las convierte automáticamente en falsas o inútiles.

## El problema cultural de la firma digital

Hay además un problema menos técnico y más humano.

Durante años, muchos sistemas implementaron la firma digital como un simple requisito burocrático: algo que debía “estar” porque la normativa lo exigía.

Eso produjo situaciones curiosas:

- documentos firmados correctamente pero imposibles de validar;
- usuarios que confunden una advertencia visual con inexistencia de firma;
- organismos que vuelven al papel porque el software muestra un mensaje ambiguo;
- y operadores que terminan confiando más en hábitos internos que en el sistema técnico.

La paradoja es que muchas veces la criptografía funciona mejor que la interfaz que intenta explicarla.

## Conclusión

Cuando un sistema dice que una firma “no valida”, muchas veces no está diciendo que el documento sea falso.

Lo que realmente está diciendo es algo bastante más específico:

> “No puedo reconstruir automáticamente toda la cadena de confianza que necesito para validar esta firma”.

Y esa diferencia importa.

Porque una firma digital no depende únicamente de matemáticas o criptografía. Depende también de infraestructura, interoperabilidad, decisiones institucionales y confianza compartida entre sistemas.

Ahí es donde normalmente aparecen los problemas reales.

---

Un certificado emitido por un certificador no autorizado no necesariamente carece de validez.

Dependiendo del marco normativo aplicable y de las condiciones concretas de uso, puede producir efectos jurídicos relevantes e incluso ofrecer garantías técnicas similares a las de un certificado emitido por una autoridad oficialmente reconocida.

La diferencia principal suele estar en el régimen probatorio y en las presunciones legales asociadas a cada tipo de firma.



