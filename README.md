# Suíte de Testes E2E com Playwright

Este repositório contém uma suíte de testes automatizados de ponta a ponta (E2E) utilizando o *Playwright*.

---

## 🚀 Começando

### Pré-requisitos
Certifique-se de que você possui o *Node.js* instalado em sua máquina.

### Instalação

1. Instale as dependências do projeto:
   bash
   npm install
   

2. Instale os navegadores suportados pelo Playwright:
   bash
   npx playwright install
   

---

## 🧪 Exemplo de Teste

O código abaixo demonstra um exemplo básico de teste end-to-end simulando navegação, checagem de títulos e interação com links:

typescript
import { test, expect } from '@playwright/test';

test('tem título', async ({ page }) => {
  await page.goto('https://playwright.dev/');

  // Espera que o título contenha a substring "Playwright"
  await expect(page).toHaveTitle(/Playwright/);
});

test('link Get Started', async ({ page }) => {
  await page.goto('https://playwright.dev/');

  // Clica no link de introdução
  await page.getByRole('link', { name: 'Get started' }).click();

  // Espera que a página tenha um cabeçalho com o nome "Installation" visível
  await expect(page.getByRole('heading', { name: 'Installation' })).toBeVisible();
});


---

## ⚙️ Como Executar os Testes

Você pode executar os testes de diferentes formas dependendo do seu objetivo:

* *Executar todos os testes (Headless):*
  bash
  npx playwright test
  
* *Executar com interface gráfica interativa (Modo UI):*
  bash
  npx playwright test --ui
  
* *Executar com o navegador visível (Headed):*
  bash
  npx playwright test --headed
  
* *Executar um teste específico:*
  bash
  npx playwright test example.spec.ts
  

---

## 📊 Relatórios

Após rodar os testes, você pode abrir o relatório detalhado em HTML executando:

bash
npx playwright show-report


---

## 📁 Estrutura do Projeto

```text
├── tests/              # Arquivos de teste do Playwright
│   └── example.spec.ts # Testes de exemplo
├── package.json        # Dependências e scripts do Node.js
└── playwright.config.ts # Arquivo de configuração do framework