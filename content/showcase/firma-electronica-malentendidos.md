---
title: "Tres malentendidos habituales sobre la firma electrónica"
description: "El discurso técnico-legal sobre firma electrónica en Paraguay repite ciertos errores con suficiente frecuencia como para que valga la pena revisarlos uno por uno."
tags: ["firma electrónica", "firma digital", "PKI", "LSC", "tecnología", "derecho"]
date: 2025-01-20
slug: "malentendidos-firma-electronica"
---

El discurso técnico-legal sobre firma electrónica en Paraguay repite ciertos errores con suficiente frecuencia como para que valga la pena revisarlos uno por uno. No son errores de mala fe: son, en su mayoría, el resultado de leer la ley sin leer la tecnología, o de leer la tecnología sin leer la ley. El problema es que combinados producen afirmaciones que suenan razonables y son, en lo sustancial, falsas o incompletas. A continuación, tres de las más comunes.

---

## 1. "La definición legal de firma electrónica es vaga"

Es habitual encontrar comentarios que lamentan que la Ley de Servicios de Confianza (LSC) defina la firma electrónica como *un conjunto de datos en formato electrónico anexos a otros datos electrónicos o asociados de manera lógica con ellos que utiliza el firmante para firmar*, y que califiquen esa definición de amplia, imprecisa o insuficiente.

La observación es comprensible pero equivocada en su diagnóstico.

En primer lugar, esa redacción no es una ocurrencia local: es una transcripción casi literal del Reglamento eIDAS de la Unión Europea, el marco normativo de referencia en materia de firma electrónica para buena parte del mundo. Si la definición es vaga, lo es deliberadamente y por las mismas razones por las que la RAE define la firma manuscrita de manera igualmente abierta: porque una ley no es un manual técnico.

En segundo lugar, la definición es estructuralmente coherente con lo que describe. Una firma electrónica *es*, en efecto, un conjunto de datos asociados a otro conjunto de datos, producidos por un tercero (el firmante). Que suene abstracto no significa que sea inexacta. Al contrario: una definición demasiado específica quedaría obsoleta con cada cambio de estándar criptográfico. La abstracción es una virtud legislativa, no un defecto.

Lo que sí podría discutirse —y eso sería una crítica útil— es si la ley local incorpora los mecanismos de supervisión e interoperabilidad que hacen que la definición tenga efectos prácticos. Eso es otra conversación.

---

## 2. "La firma electrónica simple no tiene validez jurídica plena"

Aquí es donde los errores dejan de ser de matiz y se vuelven potencialmente dañinos.

Una afirmación frecuente es que la firma electrónica *no cualificada* tiene validez jurídica limitada —válida para algunos efectos, pero no equiparable a la firma manuscrita— y que solo la firma electrónica cualificada goza de plena equivalencia legal. Esta distinción es correcta como enunciado general del eIDAS y de la LSC, pero se convierte en un error serio cuando se la usa para sugerir que la firma simple es jurídicamente débil o prescindible.

La razón es técnica y vale la pena explicarla con claridad.

**Cualquier persona puede crear una Autoridad Certificadora.** Con herramientas de libre acceso, en cuestión de minutos, es posible generar una CA propia —llamémosla *Certificadora Ilustre del Barrio*— y emitir desde ella certificados digitales con los que firmar documentos. Esa firma, por pintoresco que sea su origen, tiene validez jurídica si puede vincularse al firmante. El mecanismo de vinculación no requiere una entidad acreditada: puede ser tan simple como publicar el certificado en el sitio propio, usarlo para firmar correos, o mencionarlo en un contrato.

Lo que la cualificación aporta no es validez, sino *presunción de validez*: invierte la carga de la prueba. Una firma cualificada emitida por una entidad supervisada se presume válida salvo prueba en contrario. Una firma simple requiere que quien la presenta demuestre su autenticidad si es impugnada. Pero esa diferencia probatoria no equivale a ausencia de valor jurídico.

Dicho de otra manera: una firma emitida por una certificadora local que no cumple los estándares técnicos vigentes no es inválida por esa razón, aunque sea menos creíble que una emitida por una entidad de confianza global. Y a la inversa, una firma de una CA reconocida internacionalmente —como las que están embebidas en el software que usamos a diario— no necesita acreditación local para tener peso probatorio.

El verdadero riesgo de presentar esta distinción de manera simplista es que lleva a subestimar firmas que son perfectamente válidas, o a sobrevalorar firmas cualificadas como si fueran inimpugnables. No lo son. Una firma manuscrita puede ser discutida mediante pericia grafológica —proceso costoso y de resultado incierto—, pero una firma electrónica cualificada puede ser cuestionada si el titular sostiene, por ejemplo, que su token fue sustraído o que su contraseña fue comprometida. La solidez probatoria depende de la custodia de la clave privada, no del sello de la certificadora.

---

## 3. "Los contratos electrónicos son una categoría especial"

Un tercer error, más sutil, aparece cuando se trata la contratación electrónica como si fuera un régimen jurídico separado que requiere condiciones especiales de validez.

La LSC es clara al respecto, y en esto los comentarios suelen acertar: las partes pueden expresar oferta y aceptación mediante documentos electrónicos, salvo acuerdo en contrario. Lo que a veces se omite —o se dice de paso, sin extraer sus consecuencias— es que esto no crea una categoría nueva de contrato. Un contrato celebrado por medios telemáticos, con firmas electrónicas generadas en nombre de las partes, es un contrato. Está sujeto a las mismas reglas de formación, validez y ejecución que cualquier otro.

Esto importa porque la tendencia a tratar la firma electrónica como algo técnicamente exótico lleva a buscar requisitos donde no los hay, o a ignorar requisitos que sí existen. Un contrato de compraventa firmado con certificado SSL tiene los mismos vicios que uno firmado a mano si hay error, dolo o falta de capacidad. No hay inmunidad jurídica por el hecho de ser digital.

---

## En resumen

La firma electrónica no es magia ni es trampa. Es una tecnología con sustento legal sólido, cuya comprensión requiere leer ambas dimensiones —la técnica y la normativa— con igual cuidado. Los malentendidos más frecuentes no provienen de la complejidad intrínseca del tema, sino de leer solo una de las dos capas, o de aplicar la lógica de una al vocabulario de la otra.

La próxima vez que alguien diga que una firma electrónica simple "no tiene valor", vale la pena preguntar: ¿valor frente a quién, en qué circunstancia, y con qué nivel de custodia de la clave privada? Las respuestas suelen ser más interesantes que la pregunta.
