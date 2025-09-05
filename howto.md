Vou analisar a documentação do Mintlify para entender o formato MDX e suas features. Deixe-me explorar a estrutura e recursos disponíveis.# 📘 Guia de Formatação MDX para Documentação Mintlify

## 🎯 **Visão Geral**

Mintlify usa **MDX** (Markdown + JSX) para criar documentação rica e interativa. Este guia apresenta todos os padrões, componentes e estruturas necessários para formatar sua documentação.

---

## 📄 **1. ESTRUTURA BÁSICA DO ARQUIVO MDX**

### **Anatomia de um Arquivo MDX**

```mdx
---
title: "Título da Página"
description: "Descrição breve para SEO e navegação"
sidebarTitle: "Título Curto"
icon: "book"
iconType: "solid"
tag: "NOVO"
---

# Conteúdo da página começa aqui

Seu conteúdo em Markdown com componentes React...
```

### **Frontmatter Obrigatório**

```yaml
---
title: "Título claro e descritivo" # Obrigatório
description: "Resumo conciso da página" # Obrigatório
---
```

### **Frontmatter Opcional**

```yaml
---
sidebarTitle: "Título curto" # Para sidebar
icon: "rocket" # Ícone FontAwesome/Lucide
iconType: "solid" # Estilo do ícone
tag: "BETA" # Tag visual
mode: "wide" # Layout da página
---
```

---

## 🎨 **2. FORMATAÇÃO DE TEXTO**

### **Formatação Básica**

```markdown
**Texto em negrito**
_Texto em itálico_
~Texto tachado~
`código inline`

> Citação simples

> Citação com múltiplas linhas
>
> Segunda linha da citação
```

### **Títulos e Hierarquia**

```markdown
## Título H2 (use este como principal)

### Subtítulo H3

#### Detalhe H4
```

⚠️ **Importante**: Nunca use `# H1` no conteúdo - reserve para o frontmatter `title`

### **Listas**

```markdown
# Lista não ordenada

- Item 1
- Item 2
  - Subitem 2.1
  - Subitem 2.2

# Lista ordenada

1. Primeiro passo
2. Segundo passo
3. Terceiro passo

# Lista de tarefas

- [ ] Tarefa pendente
- [x] Tarefa concluída
```

### **Links**

```markdown
# Link externo

[Texto do link](https://exemplo.com)

# Link interno (sempre use caminho relativo)

[Veja a documentação](/docs/introduction)

# Link com título ao passar o mouse

[Link](https://exemplo.com "Título do link")
```

---

## 🧩 **3. COMPONENTES MINTLIFY**

### **3.1 Callouts (Alertas)**

```mdx
<Note>Informação suplementar útil</Note>

<Warning>Aviso importante ou breaking change</Warning>

<Tip>Melhores práticas e dicas de especialista</Tip>

<Info>Informação contextual neutra</Info>

<Check>Confirmação de sucesso</Check>

<Danger>Perigo ou ação crítica</Danger>

<!-- Callout customizado -->

<Callout icon="key" color="#FFC107" iconType="regular">
  Callout personalizado com ícone e cor
</Callout>
```

### **3.2 Cards**

```mdx
# Card simples

<Card title="Título do Card" icon="rocket">
  Conteúdo do card aqui
</Card>

# Grupo de Cards

<CardGroup cols={2}>
  <Card title="Card 1" icon="code" href="/docs/card1">
    Descrição do primeiro card
  </Card>
  <Card title="Card 2" icon="book" href="/docs/card2">
    Descrição do segundo card
  </Card>
</CardGroup>
```

### **3.3 Tabs**

````mdx
<Tabs>
  <Tab title="Python">
    ```python
    def hello():
        print("Hello World")
    ```
  </Tab>
  <Tab title="JavaScript" icon="js">
    ```javascript
    function hello() {
        console.log("Hello World");
    }
    ```
  </Tab>
  <Tab title="Ruby">
    ```ruby
    def hello
      puts "Hello World"
    end
    ```
  </Tab>
</Tabs>
````

### **3.4 Accordions**

```mdx
# Accordion único

<Accordion title="Clique para expandir">
  Conteúdo escondido que aparece ao clicar. Pode conter qualquer coisa: - Listas
  - Código - Outros componentes
</Accordion>

# Grupo de Accordions

<AccordionGroup>
  <Accordion title="Pergunta 1" icon="question-circle">
    Resposta da pergunta 1
  </Accordion>
  <Accordion title="Pergunta 2" icon="question-circle">
    Resposta da pergunta 2
  </Accordion>
</AccordionGroup>
```

### **3.5 Steps (Passos)**

````mdx
<Steps>
  <Step title="Configuração Inicial">
    Instale as dependências necessárias: ```bash npm install package ```
  </Step>
  <Step title="Configurar Ambiente">
    Crie um arquivo `.env`: ```env API_KEY=sua_chave ```
  </Step>
  <Step title="Executar Aplicação">```bash npm start ```</Step>
</Steps>
````

---

## 💻 **4. BLOCOS DE CÓDIGO**

### **Código Básico**

````mdx
```javascript
console.log("Hello World");
```
````

````

### **Código com Título e Ícone**

```mdx
```javascript App.js icon="react"
function App() {
  return <div>Hello World</div>;
}
````

````

### **Código com Destaque de Linhas**

```mdx
```python main.py lines
def calculate(x, y):
    # Esta linha será destacada
    result = x + y  # [!code highlight]
    return result
````

````

### **Código Expansível**

```mdx
```python Exemplo Longo expandable
# Código muito longo que começa colapsado
from datetime import datetime
import requests

class LongClass:
    def __init__(self):
        # ... muito código ...
        pass
````

````

### **Grupo de Códigos**

```mdx
<CodeGroup>
```bash npm
npm install package
````

```bash yarn
yarn add package
```

```bash pnpm
pnpm add package
```

</CodeGroup>
```

---

## 🖼️ **5. MÍDIA E VISUAIS**

### **Imagens**

```mdx
# Imagem simples

![Alt text descritivo](/path/to/image.png)

# Imagem com Frame (centralizada)

<Frame>![Descrição da imagem](/images/exemplo.png)</Frame>

# Frame com legenda

<Frame caption="Legenda explicativa da imagem">
  ![Dashboard](/images/dashboard.png)
</Frame>
```

### **Vídeos**

```mdx
# Vídeo HTML5

<video controls>
  <source src="/videos/tutorial.mp4" type="video/mp4" />
  Seu navegador não suporta vídeo.
</video>

# YouTube embed (se suportado)

<iframe
  width="560"
  height="315"
  src="https://www.youtube.com/embed/VIDEO_ID"
  frameborder="0"
/>
```

---

## 📊 **6. DOCUMENTAÇÃO DE API**

### **Configuração de Endpoint**

```mdx
---
title: "Criar Novo Usuário"
api: "POST https://api.exemplo.com/users"
---

## Criar um novo usuário

Endpoint para criar um novo usuário no sistema.
```

### **Parâmetros da API**

```mdx
### Parâmetros

<ParamField path="name" type="string" required>
  Nome completo do usuário
</ParamField>

<ParamField path="email" type="string" required>
  Email válido do usuário
</ParamField>

<ParamField path="age" type="number">
  Idade do usuário (opcional)
</ParamField>

<ParamField path="preferences" type="object">
  <Expandable title="propriedades">
    <ParamField path="notifications" type="boolean" default={true}>
      Receber notificações por email
    </ParamField>
    <ParamField path="theme" type="string" default="light">
      Tema da interface (light/dark)
    </ParamField>
  </Expandable>
</ParamField>
```

### **Resposta da API**

```mdx
### Resposta

<ResponseField name="id" type="string">
  ID único do usuário criado
</ResponseField>

<ResponseField name="user" type="object">
  <Expandable title="propriedades">
    <ResponseField name="name" type="string">
      Nome do usuário
    </ResponseField>
    <ResponseField name="email" type="string">
      Email do usuário
    </ResponseField>
    <ResponseField name="created_at" type="datetime">
      Data de criação
    </ResponseField>
  </Expandable>
</ResponseField>
```

### **Exemplos de Request/Response**

````mdx
<RequestExample>
```bash cURL
curl -X POST https://api.exemplo.com/users \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer TOKEN" \
  -d '{
    "name": "João Silva",
    "email": "joao@exemplo.com"
  }'
````

```javascript JavaScript
const response = await fetch("https://api.exemplo.com/users", {
  method: "POST",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer TOKEN",
  },
  body: JSON.stringify({
    name: "João Silva",
    email: "joao@exemplo.com",
  }),
});
```

</RequestExample>

<ResponseExample>
```json 200 - Sucesso
{
  "id": "usr_123456",
  "user": {
    "name": "João Silva",
    "email": "joao@exemplo.com",
    "created_at": "2024-01-15T10:30:00Z"
  }
}
```

```json 400 - Erro
{
  "error": {
    "code": "INVALID_EMAIL",
    "message": "O email fornecido é inválido"
  }
}
```

</ResponseExample>
```

---

## 🗂️ **7. CONFIGURAÇÃO DO DOCS.JSON**

### **Estrutura Básica**

```json
{
  "$schema": "https://mintlify.com/docs.json",
  "theme": "mint",
  "name": "Minha Documentação",
  "logo": {
    "dark": "/logo/dark.svg",
    "light": "/logo/light.svg"
  },
  "favicon": "/favicon.png",
  "colors": {
    "primary": "#0055FF",
    "light": "#3377FF",
    "dark": "#0044CC"
  },
  "navigation": [
    {
      "group": "Começando",
      "pages": ["introduction", "quickstart", "installation"]
    },
    {
      "group": "API Reference",
      "pages": [
        "api-reference/authentication",
        "api-reference/users",
        "api-reference/errors"
      ]
    }
  ],
  "tabs": [
    {
      "name": "API Reference",
      "url": "api-reference"
    },
    {
      "name": "Guias",
      "url": "guides"
    }
  ],
  "anchors": [
    {
      "name": "GitHub",
      "icon": "github",
      "url": "https://github.com/seu-repo"
    },
    {
      "name": "Suporte",
      "icon": "slack",
      "url": "https://slack.com/seu-workspace"
    }
  ]
}
```

---

## 🎯 **8. COMPONENTES ESPECIAIS**

### **Panel (Painel Lateral Customizado)**

````mdx
<Panel>
  <Info>
    Informação fixada no painel lateral
  </Info>
  
  <RequestExample>
    ```bash
    curl -X GET https://api.exemplo.com
    ```
  </RequestExample>
  
  <ResponseExample>
    ```json
    {"status": "success"}
    ```
  </ResponseExample>
</Panel>
````

### **Columns (Colunas)**

```mdx
<Columns cols={3}>
  <div>Coluna 1</div>
  <div>Coluna 2</div>
  <div>Coluna 3</div>
</Columns>
```

### **Conteúdo Dinâmico (com autenticação)**

```mdx
Olá, {user.firstName}!

Seu plano {user.org?.plan} inclui:

- Feature 1
- Feature 2
```

---

## ✅ **9. MELHORES PRÁTICAS**

### **Checklist de Qualidade**

- [ ] **Frontmatter completo** com `title` e `description`
- [ ] **Hierarquia correta** - começar com H2 (`##`)
- [ ] **Alt text em imagens** para acessibilidade
- [ ] **Código testado** antes de publicar
- [ ] **Links relativos** para navegação interna
- [ ] **Linguagem especificada** em blocos de código
- [ ] **Componentes apropriados** para cada tipo de conteúdo

### **Padrões de Escrita**

```markdown
✅ FAÇA:

- Use segunda pessoa ("você")
- Voz ativa e tempo presente
- Sentenças concisas
- Exemplos práticos
- Pré-requisitos no início

❌ EVITE:

- URLs absolutas internas
- Código não testado
- Assumir conhecimento prévio
- Jargão sem explicação
- Frontmatter incompleto
```

### **Estrutura Recomendada para Páginas**

```mdx
---
title: "Título Descritivo"
description: "O que o usuário vai aprender"
---

## Introdução

[Contexto e importância]

## Pré-requisitos

- Requisito 1
- Requisito 2

## Configuração

<Steps>[Passos de configuração]</Steps>

## Uso

[Exemplos práticos]

## Troubleshooting

<AccordionGroup>[Problemas comuns e soluções]</AccordionGroup>

## Próximos passos

[Links para conteúdo relacionado]
```

---

## 🚀 **10. RECURSOS AVANÇADOS**

### **Personalização com CSS**

```mdx
<div
  className="custom-class"
  style={{ backgroundColor: "#f0f0f0", padding: "20px" }}
>
  Conteúdo customizado
</div>
```

### **Ícones Customizados SVG**

```yaml
---
icon: { <svg width="24" height="24"><path d="..."/></svg> }
---
```

### **Metadados SEO**

```yaml
---
title: "Título para SEO"
description: "Descrição para mecanismos de busca"
seo:
  title: "Título customizado para SEO"
  description: "Descrição mais detalhada"
  keywords: ["palavra1", "palavra2"]
---
```

---

## 📋 **REFERÊNCIA RÁPIDA**

### **Componentes Principais**

| Componente     | Uso                          |
| -------------- | ---------------------------- |
| `<Note>`       | Informação adicional         |
| `<Warning>`    | Avisos importantes           |
| `<Tip>`        | Dicas e best practices       |
| `<Card>`       | Destacar conteúdo            |
| `<Tabs>`       | Múltiplas versões            |
| `<Steps>`      | Processos sequenciais        |
| `<Accordion>`  | Conteúdo colapsável          |
| `<CodeGroup>`  | Múltiplos exemplos de código |
| `<Frame>`      | Centralizar imagens          |
| `<ParamField>` | Documentar parâmetros API    |

### **Frontmatter Essencial**

```yaml
---
title: string # Obrigatório
description: string # Obrigatório
sidebarTitle: string # Opcional
icon: string # Opcional
tag: string # Opcional
api: string # Para endpoints
---
```

Este guia fornece tudo que você precisa para formatar documentação profissional no Mintlify. Use-o como referência ao criar suas páginas MDX!
