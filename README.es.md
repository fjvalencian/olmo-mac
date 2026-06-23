<p align="center">
  <img src="assets/olmo-icon.png" width="120" alt="Olmo" />
</p>

<p align="center"><a href="README.md">English</a> · <b>Español</b> · <a href="README.ja.md">日本語</a> · <a href="README.zh.md">中文</a></p>

# Olmo

**Un asistente de notas de reuniones con IA para macOS — open source y centrado en la privacidad.**

Olmo graba tus reuniones y llamadas, las transcribe en tiempo real y las
convierte en resúmenes en Markdown, limpios y editables — todo en tu propio Mac
y con tus propias claves de API. Ningún bot entra a tu llamada y tus notas se
quedan contigo.

## Características

- **Las dos voces de la llamada.** Captura tu micrófono *y* la voz de la otra
  persona (audio del sistema), con o sin auriculares.
- **Sin bots.** Nada entra a tu reunión — la grabación ocurre localmente en tu Mac.
- **Transcripción en tiempo real** y **resúmenes con IA**, en Markdown que puedes
  editar, buscar y guardar.
- **Tus propias claves (BYOK).** Usa tus claves de Deepgram y OpenAI; tu audio y
  tus notas nunca pasan por nuestros servidores.
- **Sincroniza con Notion.** Cada resumen se exporta solo a una página de Notion
  — una reunión, una página, sin duplicados.
- **Google Calendar.** Consulta tus reuniones y empieza a tomar notas directo
  desde tu calendario.

## Instalación

- **Descarga** el último `Olmo.dmg` desde la página de
  [Releases](https://github.com/fjvalencian/olmo-mac/releases).
  Requiere **macOS 14 o superior**.
- **Sitio web:** <https://fjvalencian.github.io/olmo-mac/>

### Compilar desde el código

Requisitos: macOS 14+, Xcode 15+ y
[XcodeGen](https://github.com/yonaskolb/XcodeGen) (`brew install xcodegen`).

```bash
git clone https://github.com/fjvalencian/olmo-mac.git
cd olmo-mac/Olmo-MacOS
xcodegen generate
open Olmo-MacOS.xcodeproj   # luego ⌘R
```

## Tecnología

SwiftUI (macOS 14+) · AVFoundation + ScreenCaptureKit (micrófono + audio del
sistema) · Deepgram (voz a texto) · OpenAI (resúmenes) · Core Data
(almacenamiento local) · APIs de Google Calendar y Notion.

## Contribuir

Las contribuciones son bienvenidas — mira [CONTRIBUTING.md](CONTRIBUTING.md).
¿Encontraste un error o tienes una idea? Abre un
[issue](https://github.com/fjvalencian/olmo-mac/issues).

## Licencia

[MIT](LICENSE).
