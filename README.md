Lando: Base para Drupal
===

Plantilla/Esqueleto para proyectos Drupal con [Lando](https://lando.dev/).

[![version][version-badge]][changelog]
[![Licencia][license-badge]][license]
[![Código de conducta][conduct-badge]][conduct]

[![Donate][donate-badge]][donate-url] <img src="https://img.shields.io/liberapay/patrons/ONovasDev.svg?logo=liberapay">

---

## Información

Esta es una plantilla que permite integrar nuestros proyectos Drupal para el
desarrollo con Lando.

Los contenedores que se montan son (6 + 1 que sería de proxy):
- Apache (appserver)
- MariaDB (database)
- Adminer (adminer)
- Redys (cache)
- Chrome Driver (chromedriver)
- Mailpit (mailpit)

---

## Requisitos

Los requisitos son los mismos que para [Lando](https://lando.dev/), no tenemos
ningún requisito especial.

---

## Instalación

Sólo es necesario copiar los siguientes archivos/directorios en la raíz del
proyecto:
- .lando
- .vscode
- .lando.yml

Se debe modificar el archivo .lando.yml el texto [NOMBRE_PROYECTO] por el nombre
que deseemos y el texto [PASSWORD] por la contraseña de la base de datos.

No debemos olvidarnos que deberemos configurar el archivo `settings.php` con los
datos de conexión pertinentes (sustituyendo las mismas cadenas de antes):

```php
$databases['default']['default'] = [
  'database' => '[NOMBRE_PROYECTO]',
  'username' => 'u[NOMBRE_PROYECTO]',
  'password' => '[PASSWORD]',
  'prefix'   => '',
  'host'     => 'database.[NOMBRE_PROYECTO].internal',
  'port'     => 3306,
  ...
];
```
> [!NOTE]
> Se recomienda el uso del script [iniciar-proyecto](https://github.com/oscarnovasf/iniciar-proyecto).

---
⌨️ con ❤️ por [Óscar Novás][mi-web] 😊

[mi-web]: https://oscarnovas.com "for developers"

[version]: v1.0.0
[version-badge]: https://img.shields.io/badge/Versión-1.0.0-blue.svg

[license]: LICENSE.md
[license-badge]: https://img.shields.io/badge/Licencia-GPLv3+-green.svg "Leer la licencia"

[conduct]: CODE_OF_CONDUCT.md
[conduct-badge]: https://img.shields.io/badge/C%C3%B3digo%20de%20Conducta-2.0-4baaaa.svg "Código de conducta"

[changelog]: CHANGELOG.md "Histórico de cambios"

[donate-badge]: https://img.shields.io/badge/Donaci%C3%B3n-PayPal-red.svg
[donate-url]: https://paypal.me/oscarnovasf "Haz una donación"
