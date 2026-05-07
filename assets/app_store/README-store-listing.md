# Ficha de tienda (App Store Connect)

Plantillas multi-idioma de los campos localizables que App Store Connect pide en **App Store → Información de la versión** y en **Información general** de la app. Todo el texto es **ejemplo** y debe sustituirse antes de enviar a revisión.

## Límites por campo

| Campo                                | Límite                     | Notas                                                                     |
| ------------------------------------ | -------------------------- | ------------------------------------------------------------------------- |
| Name (nombre)                        | **30** caracteres          | Aparece en la ficha y en la búsqueda.                                     |
| Subtitle (subtítulo)                 | **30** caracteres          | Resumen corto bajo el nombre.                                             |
| Promotional Text (texto promocional) | **170** caracteres         | Editable sin nuevo build.                                                 |
| Description (descripción)            | **4000** caracteres        | Texto principal de la ficha.                                              |
| Keywords (palabras clave)            | **100** caracteres totales | Separadas por coma, sin espacios extra. No usar nombres de marcas ajenas. |
| Support URL                          | URL pública                | Obligatoria.                                                              |
| Marketing URL                        | URL pública                | Opcional.                                                                 |
| Copyright                            | `YYYY Nombre o Entidad`    | Obligatorio. Sin URLs.                                                    |
| Version                              | Formato `X.Y.Z`            | Debe coincidir con `CFBundleShortVersionString` del build subido.         |

## Idiomas a localizar

Los listados aquí coinciden con los disponibles en App Store Connect (las claves entre paréntesis son las que la consola muestra al añadir un idioma):

- `en-US` Inglés (EE. UU.) — Primary
- `zh-Hans` Chino (simplificado)
- `fr-FR` Francés
- `de-DE` Alemán
- `ja` Japonés
- `ko` Coreano
- `pt-BR` Portugués (Brasil)
- `ru` Ruso
- `es-MX` Español (México)

Los textos marcados como `[EJEMPLO]` / `EXAMPLE` / `【例】` / `[ПРИМЕР]` / `【示例】` son **solo plantilla**.

---

## Valores globales de referencia (un solo idioma de trabajo)

Esqueleto previo a localizar. No se pega directamente en la consola; sirve para preparar las traducciones.

**Name (máx. 30 caracteres)**

```
EJEMPLO: App plantilla
```

**Subtitle (máx. 30 caracteres)**

```
[EJEMPLO] Subtítulo de demo
```

**Promotional Text (máx. 170 caracteres)**

```
[EJEMPLO] Texto promocional de muestra. Sustituir por novedades reales antes de publicar la versión.
```

**Description (máx. 4000 caracteres)**

```
[EJEMPLO] Descripción extendida de demostración.

Este párrafo forma parte de una plantilla para la ficha de App Store. Debe describir funciones reales, datos tratados y cualquier información que Apple exija para tu categoría.

Sustituir todo el contenido por texto definitivo revisado antes del envío a revisión.
```

**Keywords (máx. 100 caracteres totales, separados por coma)**

```
ejemplo,plantilla,demo,app,prueba
```

**Support URL**

```
https://example.com/soporte
```

**Marketing URL**

```
https://example.com
```

**Copyright**

```
2026 App Template
```

**Version**

```
1.0.0
```

---

### English (EE. UU.) — `en-US` (Primary)

**Name (máx. 30 caracteres)**

```
EXAMPLE: Demo App EN
```

**Subtitle (máx. 30 caracteres)**

```
[EXAMPLE] Demo subtitle EN
```

**Promotional Text (máx. 170 caracteres)**

```
[EXAMPLE] Sample promotional copy. Replace with real release highlights before publishing the version.
```

**Description (máx. 4000 caracteres)**

```
[EXAMPLE] Full-length demo description for the App Store listing.

This paragraph is placeholder copy. Replace with accurate features, data practices, and any disclosure required for your product category. The App Store allows up to 4000 characters; this sample is intentionally brief.
```

**Keywords (máx. 100 caracteres totales, separados por coma)**

```
example,template,demo,app,sample
```

**Support URL**

```
https://example.com/support
```

**Marketing URL**

```
https://example.com
```

**Copyright**

```
2026 App Template
```

**Version**

```
1.0.0
```

---

### 中文（简体）— `zh-Hans`

**Name (máx. 30 caracteres)**

```
【示例】演示应用 ZH
```

**Subtitle (máx. 30 caracteres)**

```
【示例】演示副标题
```

**Promotional Text (máx. 170 caracteres)**

```
【示例】宣传文案占位文本。发布版本前请替换为真实的更新亮点。
```

**Description (máx. 4000 caracteres)**

```
【示例】这是 App Store 完整说明的演示内容。

请替换为真实功能与数据处理说明。字数上限为4000字，本段仅为示例并故意缩短。
```

**Keywords (máx. 100 caracteres totales, separados por coma)**

```
示例,模板,演示,应用,测试
```

**Support URL**

```
https://example.com/zh/support
```

**Marketing URL**

```
https://example.com/zh
```

**Copyright**

```
2026 App Template
```

**Version**

```
1.0.0
```

---

### Français — `fr-FR`

**Name (máx. 30 caracteres)**

```
EXEMPLE: Appli démo FR
```

**Subtitle (máx. 30 caracteres)**

```
[EXEMPLE] Sous-titre démo
```

**Promotional Text (máx. 170 caracteres)**

```
[EXEMPLE] Texte promotionnel de démonstration. À remplacer par les nouveautés réelles avant publication.
```

**Description (máx. 4000 caracteres)**

```
[EXEMPLE] Description longue de démonstration pour la fiche App Store.

Ce texte est un exemple. Remplace-le par une description fidèle aux fonctionnalités et aux données traitées. La limite est de 4000 caractères ; cet extrait est volontairement court.
```

**Keywords (máx. 100 caracteres totales, separados por coma)**

```
exemple,modele,demo,application,test
```

**Support URL**

```
https://example.com/fr/support
```

**Marketing URL**

```
https://example.com/fr
```

**Copyright**

```
2026 App Template
```

**Version**

```
1.0.0
```

---

### Deutsch — `de-DE`

**Name (máx. 30 caracteres)**

```
BEISPIEL: Demo-App DE
```

**Subtitle (máx. 30 caracteres)**

```
[BEISPIEL] Demo-Untertitel
```

**Promotional Text (máx. 170 caracteres)**

```
[BEISPIEL] Werbetext-Platzhalter. Vor der Veröffentlichung durch echte Neuerungen ersetzen.
```

**Description (máx. 4000 caracteres)**

```
[BEISPIEL] Ausführliche Demobeschreibung für die App-Store-Eintragung.

Dieser Absatz ist Platzhalter. Hier würdest du echte Funktionen, Datenpraktiken und Hinweise für Nutzer ergänzen. Maximal 4000 Zeichen laut App Store Connect — dieser Text ist nur verkürzt.
```

**Keywords (máx. 100 caracteres totales, separados por coma)**

```
beispiel,vorlage,demo,app,test
```

**Support URL**

```
https://example.com/de/support
```

**Marketing URL**

```
https://example.com/de
```

**Copyright**

```
2026 App Template
```

**Version**

```
1.0.0
```

---

### 日本語 — `ja`

**Name (máx. 30 caracteres)**

```
【例】デモアプリ JP
```

**Subtitle (máx. 30 caracteres)**

```
【例】デモ用のサブタイトル
```

**Promotional Text (máx. 170 caracteres)**

```
【例】プロモーション用のサンプル文です。バージョン公開前に実際の更新内容に差し替えてください。
```

**Description (máx. 4000 caracteres)**

```
【例】App Store 向けの長文説明のサンプルです。

実際の機能やデータの取り扱いなどを記載してください。文字数上限は4000文字です。この文はデモ用に短くしています。
```

**Keywords (máx. 100 caracteres totales, separados por coma)**

```
例,テンプレート,デモ,アプリ,サンプル
```

**Support URL**

```
https://example.com/ja/support
```

**Marketing URL**

```
https://example.com/ja
```

**Copyright**

```
2026 App Template
```

**Version**

```
1.0.0
```

---

### 한국어 — `ko`

**Name (máx. 30 caracteres)**

```
[예시] 데모 KR
```

**Subtitle (máx. 30 caracteres)**

```
[예시] 데모 부제
```

**Promotional Text (máx. 170 caracteres)**

```
[예시] 프로모션 샘플 문구입니다. 버전 게시 전에 실제 업데이트 내용으로 교체하세요.
```

**Description (máx. 4000 caracteres)**

```
[예시] App Store 상세 설명 예시입니다.

실제 기능과 데이터 처리 내용으로 교체해야 합니다. 최대 4000자이며 본문은 데모용으로 짧게 작성했습니다.
```

**Keywords (máx. 100 caracteres totales, separados por coma)**

```
예시,템플릿,데모,앱,샘플
```

**Support URL**

```
https://example.com/ko/support
```

**Marketing URL**

```
https://example.com/ko
```

**Copyright**

```
2026 App Template
```

**Version**

```
1.0.0
```

---

### Português (Brasil) — `pt-BR`

**Name (máx. 30 caracteres)**

```
EXEMPLO: App demo PT
```

**Subtitle (máx. 30 caracteres)**

```
[EXEMPLO] Subtítulo demo
```

**Promotional Text (máx. 170 caracteres)**

```
[EXEMPLO] Texto promocional de demonstração. Substituir pelos destaques reais antes de publicar a versão.
```

**Description (máx. 4000 caracteres)**

```
[EXEMPLO] Descrição longa de exemplo para a listagem na App Store.

Substitua por texto real sobre recursos e dados tratados. O limite é de 4000 caracteres; esta amostra foi encurtada de propósito.
```

**Keywords (máx. 100 caracteres totales, separados por coma)**

```
exemplo,modelo,demo,app,teste
```

**Support URL**

```
https://example.com/pt/suporte
```

**Marketing URL**

```
https://example.com/pt
```

**Copyright**

```
2026 App Template
```

**Version**

```
1.0.0
```

---

### Русский — `ru`

**Name (máx. 30 caracteres)**

```
ПРИМЕР: Демо RU
```

**Subtitle (máx. 30 caracteres)**

```
[ПРИМЕР] Подзаголовок демо
```

**Promotional Text (máx. 170 caracteres)**

```
[ПРИМЕР] Промо-текст-заглушка. Перед публикацией версии замените на реальные нововведения.
```

**Description (máx. 4000 caracteres)**

```
[ПРИМЕР] Длинное демонстрационное описание для карточки приложения в App Store.

Замените на точное описание функций и данных. Лимит — 4000 символов; этот текст сокращён как пример.
```

**Keywords (máx. 100 caracteres totales, separados por coma)**

```
пример,шаблон,демо,приложение,тест
```

**Support URL**

```
https://example.com/ru/support
```

**Marketing URL**

```
https://example.com/ru
```

**Copyright**

```
2026 App Template
```

**Version**

```
1.0.0
```

---

### Español (México) — `es-MX`

**Name (máx. 30 caracteres)**

```
EJEMPLO: App demo ES
```

**Subtitle (máx. 30 caracteres)**

```
[EJEMPLO] Subtítulo demo
```

**Promotional Text (máx. 170 caracteres)**

```
[EJEMPLO] Texto promocional de muestra. Sustituir por novedades reales antes de publicar la versión.
```

**Description (máx. 4000 caracteres)**

```
[EJEMPLO] Descripción larga de ejemplo para la ficha de la App Store.

Este contenido es ficticio. Aquí debe figurar la información real sobre la app, datos tratados y funciones principales. El límite en App Store es 4000 caracteres; esta muestra está acortada a propósito.
```

**Keywords (máx. 100 caracteres totales, separados por coma)**

```
ejemplo,plantilla,demo,app,prueba
```

**Support URL**

```
https://example.com/es/soporte
```

**Marketing URL**

```
https://example.com/es
```

**Copyright**

```
2026 App Template
```

**Version**

```
1.0.0
```
