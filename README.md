# IOCs - Campaña de smishing/phishing suplantando multas de tránsito de Monterrey

Este repositorio contiene indicadores de compromiso sanitizados relacionados con una campaña activa de smishing/phishing que suplanta un portal de pago de multas de tránsito de Monterrey, Nuevo León, México.

El objetivo de este repositorio es apoyar labores defensivas de:

* bloqueo preventivo;
* threat hunting;
* monitoreo de infraestructura;
* respuesta a incidentes;
* concientización ciudadana;
* coordinación de takedown;
* apoyo a equipos antifraude e instituciones afectadas.

No se incluye información sensible, datos de víctimas, tokens de sesión, respuestas completas del backend ni código completo del kit.

---

## Clasificación

* Smishing
* Phishing
* Fraude financiero
* Suplantación de entidad gubernamental
* Robo de credenciales/datos bancarios
* Captura de OTP, NIP dinámico, CVV dinámico y validaciones de app bancaria

---

## Indicadores principales

### Dominio

```text
monterreygob1[.]one
```

### URL observada

```text
hxxps://monterreygob1[.]one/mx
```

### IP observada

```text
43.130.90[.]167
```

---

## Endpoints observados

```text
hxxps://monterreygob1[.]one/VNUmpvhrfN/api
hxxps://monterreygob1[.]one/VNUmpvhrfN/api/input
wss://monterreygob1[.]one/ws?token=<uuid>
```

---

## Artefactos observados

```text
/ww_gb_Ticket_temp3/header.html
/ww_gb_Ticket_temp3/footer.html
/uploads/*.jpg
/uploads/*.png
```

---

## Tecnologías observadas

```text
Caddy
GoFrame HTTP Server
WebSocket
Vue SPA
OpenSSH 9.6p1 Ubuntu
DNS recursivo expuesto en 53/tcp y 53/udp
```

---

## Marcas / temas observados en plantillas

Las plantillas observadas hacen referencia a flujos de validación asociados a:

```text
Santander
Banorte
HSBC
BBVA
Apple Store
Radiomóvil Dipsa
Google
BANORTEL
```

Esto no implica responsabilidad de dichas marcas o instituciones. Se mencionan únicamente como posibles temas usados por el kit de phishing.

---

## Strings de pivote

```text
VNUmpvhrfN
ww_gb_Ticket_temp3
桑坦德8位
北方验证
HSBC验证
BBVA动态CVV
自定义APP验证
submitAppValidCode
submitCustomOtpValid
Pago agotado, por favor realice el pago con la tarjeta del Banco del Norte.
```

---

## Hashes SHA256 de artefactos públicos analizados

```text
44f37d1b0c5f620b138152a17e0f264a17a5975fe4df595ab14ddc22d298d180  index.pretty.js
47ea8b61e1c2d854ae1b693453297db01e75dafe3d7b1a842b7183c236a6b2a0  custom_config.json
73d170ee39bf95e2cadc546980b513e7e5dff93cf751a99a276f511499e1f4ce  api_bootstrap_body.json
44a8a0b5e96bd99460a1cf73ae2dddec55b455d943ee012bea68c9ab1a141278  header.html
```

Nota: algunos hashes corresponden a artefactos usados únicamente para correlación técnica. No se publica el contenido completo de archivos sensibles.

---

## Hallazgos técnicos resumidos

* El dominio observado suplanta visualmente un portal de multas de tránsito.
* La infraestructura cuenta con backend activo.
* Se observó uso de WebSocket para control de sesión.
* Se identificó un endpoint de configuración dinámica del kit.
* Se identificó un endpoint para recepción de eventos/input.
* La configuración observada contiene plantillas bancarias dinámicas.
* Se observaron plantillas relacionadas con validaciones OTP, NIP dinámico, SuperToken, CVV dinámico y app bancaria.
* Se identificaron cadenas en chino dentro de nombres de plantillas y comentarios.
* Se observaron assets públicos bajo `/uploads/`.
* Se observó posible exposición de DNS recursivo en la IP analizada.

---

## Referencia comunitaria

VirusTotal Community:

```text
https://www.virustotal.com/gui/url/d7b388943512e04b304dc982233cdac8a80336b012a3f1237260c6f0ff628652/community
```

---

## Recomendaciones defensivas

### Para ciudadanos

* Verificar que el dominio sea oficial antes de realizar pagos o trámites.
* No abrir enlaces recibidos por SMS, WhatsApp o redes sociales sin validar.
* No ingresar datos bancarios en sitios sospechosos o dominios no institucionales.
* Desconfiar de sitios que soliciten OTP, NIP dinámico, CVV o validaciones de app bancaria.
* Reportar enlaces sospechosos a la institución correspondiente.

### Para instituciones

* Bloquear dominio, URL e IP en DNS, proxy, EDR y gateways de seguridad.
* Monitorear dominios similares a marcas institucionales.
* Implementar detección temprana de typosquatting y brand impersonation.
* Coordinar takedown con registrar, hosting, navegadores y proveedores de reputación.
* Preservar evidencia técnica antes de la baja de infraestructura.
* Notificar a bancos y equipos antifraude cuando existan flujos de captura bancaria.

---

## Aviso

Este repositorio se publica con fines defensivos, educativos y de concientización.
No contiene datos de víctimas, credenciales, tokens, payloads ofensivos ni código completo del kit.

La evidencia técnica completa debe compartirse únicamente por canales formales con instituciones, equipos antifraude, proveedores de infraestructura, CERTs y autoridades competentes.
