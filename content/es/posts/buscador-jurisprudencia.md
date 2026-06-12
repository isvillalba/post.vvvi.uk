---
title: "El buscador que no busca"
date: 2026-06-11
draft: false
tags: ["jurisprudencia", "tecnología jurídica", "CSJ", "Paraguay"]
description: "El buscador oficial de jurisprudencia de la Corte Suprema de Justicia no encuentra resoluciones porque, estructuralmente, no puede encontrarlas. Una alternativa existe."
---

El buscador de jurisprudencia de la Corte Suprema de Justicia del Paraguay —disponible en [csj.gov.py/jurisprudencia](https://www.csj.gov.py/jurisprudencia/)— es, en sentido estricto, un buscador de metadatos. Busca número de expediente, partes, sala, fecha. No busca el texto de las resoluciones. Esto ya sería una limitación considerable para quien investiga doctrina o precedentes. Pero hay algo más.

Aproximadamente un tercio de las resoluciones publicadas en el portal no tienen metadatos asociados. No es un error técnico menor ni un problema de sincronización pendiente: es una laguna estructural que lleva años. Una resolución sin metadatos es, para ese buscador, una resolución que no existe.

El resultado práctico es conocido por cualquier abogado que haya intentado usar la herramienta con seriedad: se busca, no se encuentra, y se concluye que la jurisprudencia no existe o que uno está buscando mal. Pocas veces se llega a la conclusión correcta: que el sistema *se supone que no encuentre*.

---

Hace un tiempo construí un buscador alternativo, disponible en [csj.vvvi.uk](https://csj.vvvi.uk), que opera sobre una base de datos de texto completo extraída de las mismas resoluciones publicadas por la CSJ. No busca metadatos. Busca el texto de los documentos — el razonamiento, la cita, la doctrina, las palabras que un juez o un abogado efectivamente escribió.

La diferencia no es de velocidad ni de interfaz. Es de concepto: un abogado no busca "Acuerdo y Sentencia N° 412 del Tribunal de Apelación Civil y Comercial, Segunda Sala". Busca *error material en liquidación de condena*, o *caducidad de instancia en proceso ejecutivo*, o *nulidad por falta de fundamentación*. Eso es lo que el buscador oficial no puede dar, y lo que este intenta ofrecer.

La herramienta es modesta, en desarrollo permanente, y —como todo lo que se construye fuera de una institución— imperfecta. Pero busca donde el otro no llega. A veces eso es suficiente.

