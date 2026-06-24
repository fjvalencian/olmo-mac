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
- **Sitio web:** <https://getolmo.app/>

### Compilar desde el código

Requisitos: macOS 14+, Xcode 15+ y
[XcodeGen](https://github.com/yonaskolb/XcodeGen) (`brew install xcodegen`).

```bash
git clone https://github.com/fjvalencian/olmo-mac.git
cd olmo-mac/Olmo-MacOS
xcodegen generate
open Olmo-MacOS.xcodeproj   # luego ⌘R
```


## Claves de API (BYOK)

Olmo es **bring-your-own-keys**: conectas tus propias cuentas de Deepgram y
OpenAI, así tu audio y tus notas van directo a los servicios que *tú* controlas —
nunca pasan por un servidor nuestro.

### ¿Por qué Deepgram?

Olmo transcribe **en vivo, mientras hablas**, así que necesita un speech-to-text
rápido, preciso y en tiempo real. Deepgram está hecho justo para eso: streaming
de baja latencia, buena precisión y soporte multilingüe, y un modelo simple de
**pago por uso** sin suscripción. Las cuentas nuevas reciben **$200 en créditos
gratis** y sin tarjeta — muchas reuniones antes de pagar nada.

> Los $200 son un **crédito único de registro** (caduca un año después de
> registrarte), no un cupo mensual. Cuando se acaba, solo pagas por lo que
> transcribes, con tarifas de pago por uso.

**Consigue tu clave:**

1. Regístrate en [console.deepgram.com/signup](https://console.deepgram.com/signup) — gratis, sin tarjeta.
2. En la consola, ve a **API Keys → Create a New API Key** y cópiala.
3. En Olmo, abre **Ajustes → Claves de API** y pégala en el campo de Deepgram.

Tu **clave de OpenAI** se configura igual (es la que genera los resúmenes con IA).


## Privacidad y seguridad

Olmo está hecho para que tus conversaciones sigan siendo tuyas.

- **Local primero.** Tus grabaciones y notas se guardan **en tu Mac** (Core Data). No se suben a ningún servidor de Olmo.
- **Sin intermediario de Olmo (BYOK).** La transcripción y los resúmenes usan **tus propias** claves de Deepgram y OpenAI — esos datos van a *tus* cuentas en esos servicios, no a un servidor nuestro.
- **Sin rastreo.** Ningún SDK de analítica, telemetría ni publicidad. Olmo no "llama a casa".
- **Claves a salvo.** Tus claves de API y tokens se guardan en el **Keychain de macOS** (solo en el dispositivo, fuera de iCloud).
- **Integraciones opt-in.** Notion y Google Calendar solo se contactan cuando *tú* los conectas, con *tu* token/cuenta, para las acciones que autorices.
- **Permisos que tú controlas.** Olmo pide micrófono (tu voz) y grabación de pantalla (para captar el audio del sistema de la otra persona). Los concedes en macOS y los puedes revocar cuando quieras.
- **Open source.** No tienes que creernos — el código está aquí para que lo leas y lo verifiques.

> Nota honesta: para convertir voz en texto y texto en resúmenes, el audio y las transcripciones se envían a los servicios que elijas (Deepgram, OpenAI) con tus propias claves. Olmo no puede hacerlo del todo en el dispositivo — pero son *tus* cuentas y *tus* datos, y nada se guarda en un servidor de Olmo.

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
