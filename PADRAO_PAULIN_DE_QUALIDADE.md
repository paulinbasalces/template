# PADRÃO PAULIN DE QUALIDADE
## Sites editoriais, educacionais, diretórios e plataformas de conteúdo
### Versão 1.1 — Google Ads + LGPD + WCAG + EEAT + SEO + Performance

---

# OBJETIVO

Elevar qualquer site estático ou semiestático ao padrão profissional utilizado no projeto Estudar Online, garantindo conformidade simultânea com:

- Google Ads
- Google AdSense
- Google Publisher Policies
- Google Search
- Google Lighthouse
- WCAG 2.2
- LGPD
- EEAT
- Core Web Vitals
- SEO Técnico
- GitHub Pages

---

# REGRA PRINCIPAL

NUNCA alterar:

- identidade visual;
- branding;
- logotipo;
- conceito visual;
- linguagem editorial;
- tipografia principal;
- paleta de cores;
- layout estrutural.

Realizar apenas correções de:

- conformidade;
- segurança;
- acessibilidade;
- SEO;
- performance;
- monetização;
- credibilidade;
- estrutura editorial.

---

# REGRA DE ENTREGA

Nunca entregar:

- instruções;
- pseudocódigo;
- apenas trechos;
- sugestões abstratas.

Sempre entregar:

✅ arquivo completo;
✅ pronto para copiar e colar;
✅ compatível com GitHub Pages;
✅ mantendo a identidade visual;
✅ preservando regras de negócio.

---

# ESTRUTURA MÍNIMA DO PROJETO

```text
/
├── index.html
├── style.css
├── script.js
├── sitemap.xml
├── robots.txt
├── ads.txt
├── manifest.webmanifest
├── humans.txt
├── dados.json
├── sobre.html
├── contato.html
├── privacidade.html
├── cookies.html
├── termos.html
├── politica-publicidade.html
```

---

# BANCO DE DADOS (OBRIGATÓRIO)

## REGRA PRINCIPAL

Padronizar todos os bancos JSON utilizando nomenclatura única.

NUNCA utilizar:

```json
"area"
"category"
"tipo"
"segmento"
"grupo"
"classe"
```

Utilizar SEMPRE:

```json
"categoria"
```

---

## Estrutura mínima obrigatória

```json
{
    "id": 1,
    "nome": "",
    "categoria": "",
    "descricao": "",
    "dor_resolvida": "",
    "url": "",
    "emoji": ""
}
```

---

## Regras

### id

- obrigatório;
- único;
- inteiro.

---

### nome

- obrigatório;
- string;
- sem HTML.

---

### categoria

- obrigatório;
- string;
- padronizada.

Exemplo:

```json
"categoria": "Programação"
```

---

### descricao

- obrigatório;
- texto editorial.

---

### dor_resolvida

- obrigatório;
- problema que resolve.

---

### url

- obrigatório;
- https.

---

### emoji

- obrigatório;
- único emoji.

---

# REGRA DE FALLBACK

Todo script deve possuir:

```javascript
function obterCategoria(item){

    return (
        item.categoria ||
        item.area ||
        item.category ||
        "Outros"
    ).trim();

}
```

---

# ESTRUTURA SEO

Obrigatório:

```html
<title>
<meta charset>
<meta viewport>
<meta description>
<meta robots>
<link rel="canonical">
```

---

# OPEN GRAPH

Obrigatório:

```html
og:title
og:description
og:image
og:url
og:type
```

---

# TWITTER

Obrigatório:

```html
twitter:card
twitter:title
twitter:description
twitter:image
```

---

# STRUCTURED DATA

Implementar:

```json
Organization
WebSite
Article
BreadcrumbList
FAQPage
```

---

# GOOGLE ADS

Obrigatório:

```text
ads.txt
```

Conteúdo:

```text
google.com, pub-XXXXXXXXXXXX, DIRECT, f08c47fec0942fa0
```

---

# CONSENT MODE V2

Implementar:

```javascript
ad_storage
analytics_storage
ad_user_data
ad_personalization
```

---

# LGPD

Obrigatório:

```text
privacidade.html
cookies.html
termos.html
```

Implementar:

- aceitar;
- recusar;
- persistência;
- atualização GTM.

---

# GOOGLE TAG MANAGER

Implementar:

```html
HEAD
BODY
```

Eventos:

```javascript
site_pronto
busca
categoria
abrir_modal
compartilhar
erro
```

---

# SEGURANÇA

Implementar:

```html
Content-Security-Policy
```

---

Obrigatório:

```html
rel="noopener noreferrer"
```

---

Evitar:

```javascript
innerHTML inseguro
```

---

Implementar:

```javascript
window.onerror
window.unhandledrejection
```

---

# ACESSIBILIDADE

Garantir:

## contraste

AA mínimo.

---

## foco

```css
:focus-visible
```

---

## skip links

```html
skip-to-content
```

---

## aria

```html
aria-label
aria-expanded
aria-controls
aria-hidden
aria-busy
```

---

## modal

Implementar:

- focus trap;
- ESC;
- restauração de foco.

---

## motion

Implementar:

```css
@media(prefers-reduced-motion)
```

---

## área clicável

Mínimo:

```css
44px
```

---

# PERFORMANCE

Implementar:

## debounce

```javascript
setTimeout
```

---

## imagens

```html
loading="lazy"
decoding="async"
```

---

## scripts

```html
async
defer
```

---

## renderização

Implementar:

- cache;
- lazy render;
- fragment rendering.

---

# PWA

Criar:

```text
manifest.webmanifest
```

Implementar:

```json
name
short_name
icons
theme_color
background_color
display
orientation
```

---

# ARQUIVOS TÉCNICOS

Obrigatórios:

```text
robots.txt
sitemap.xml
humans.txt
```

---

# HUMANS.TXT

Exemplo:

```text
Owner:
Contact:
Project:
Technology:
Standards:
```

---

# EEAT

Obrigatório:

## Sobre

- autor;
- metodologia;
- critérios;
- curadoria.

---

## Transparência

- monetização;
- publicidade;
- afiliados;
- conflitos.

---

## Contato

- e-mail válido;
- canal institucional.

---

## Atualização

Exibir:

```text
Última atualização
```

---

# RODAPÉ PROFISSIONAL

Estrutura obrigatória:

## Coluna 1

```text
Marca
Descrição
Missão
```

---

## Coluna 2

```text
Sobre
Contato
Publicidade
Curadoria
```

---

## Coluna 3

```text
Privacidade
Cookies
Termos
Sitemap
Robots
```

---

## Coluna 4

```text
Transparência
Afiliados
Monetização
Critérios editoriais
```

---

## Rodapé inferior

```text
© Ano
Todos os direitos reservados

Feito na América Latina
para democratizar o acesso
ao conhecimento digital.
```

---

# RESPONSIVIDADE

Validar:

- Desktop
- Notebook
- Tablet
- Mobile
- Mobile Landscape

---

# CORE WEB VITALS

Objetivos:

```text
LCP < 2,5s
CLS < 0,1
INP < 200ms
```

---

# LIGHTHOUSE

Objetivos:

```text
Performance > 90
Accessibility > 95
Best Practices > 95
SEO > 95
```

---

# GOOGLE

Objetivos:

```text
Google Ads.............95%+
Google Publisher.......95%+
LGPD..................100%
WCAG...................95%+
SEO....................95%+
Lighthouse.............90%+
EEAT...................95%+
Core Web Vitals........90%+
```

---

# DEFINIÇÃO DO PADRÃO

Este documento define o:

# PADRÃO PAULIN DE QUALIDADE

para sites:

- editoriais;
- educacionais;
- diretórios;
- afiliados;
- hubs de conteúdo;
- plataformas de curadoria;
- projetos hospedados em GitHub Pages.
