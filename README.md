# 📋 Sistema de Emissão de Recibos

Sistema web (PWA) para emissão de recibos e pedidos comerciais com importação automática de preços via Excel e impressão em formato A4.

> **🚀 [Veja o GUIA DE INÍCIO RÁPIDO](INICIO-RAPIDO.md)** para começar em 2 minutos!

## 🌐 Como Acessar

**Página Principal**: Abra `index.html` no seu navegador

### URIs Funcionais do Sistema:
- **`/` ou `index.html`** - Página de boas-vindas com menu
- **`/sistema.html`** - Sistema de cadastro e emissão de recibos
- **`/print.html`** - Visualização e impressão (acesso via botão no sistema)
- **`/gerar-exemplo.html`** - Gera planilha Excel de exemplo
- **`/ajuda-planilha.html`** - Tutorial completo sobre a planilha

## ✨ Funcionalidades Implementadas

### ✅ Recursos Principais
- **Importação de tabela de preços** via arquivo Excel (.xlsx)
- **Busca automática de produtos por código**
- **Adição de itens ao pedido** com cálculo automático de totais
- **Gerenciamento de itens** (adicionar e remover)
- **Persistência de dados** com localStorage (não perde dados ao atualizar)
- **Visualização e impressão** em layout A4 profissional
- **Exportação para PDF** (via "Salvar como PDF" na impressão)
- **Layout responsivo** (funciona em desktop, tablet e celular)

### 📄 Página de Impressão
Layout baseado no modelo fornecido, incluindo:
- Cabeçalho com faixa decorativa vermelha
- Espaço para logomarca da empresa
- Informações cadastrais (CNPJ, endereço, banco, contato)
- Campos "Cliente" e "Data de Abertura"
- Tabela de itens com colunas: ITEM, DESCRIÇÃO, UNID, QUANT, UNIT, V.TOTAL
- Total do lote em destaque
- Marca d'água geométrica centralizada
- Rodapé com dados da empresa e responsável

## 📊 Estrutura da Planilha Excel

Para o sistema funcionar corretamente, sua planilha Excel (.xlsx) deve ter as seguintes colunas:

### Formato Obrigatório

| codigo | descricao | unid | VALOR UNIT |
|--------|-----------|------|------------|
| 001 | TOCA SANFONADA | PCT/100 | 17,00 |
| 002 | LUVA CIRURGICA | CX | 87,00 |
| 003 | MASCARA N95 | PCT/20 | 45,50 |

### 📝 Descrição das Colunas

- **codigo** (obrigatório): Código único do produto (pode ser texto ou número)
- **descricao** (obrigatório): Nome/descrição completa do produto
- **unid** (opcional): Unidade de medida (ex: PCT/100, CX, UN, KG)
- **VALOR UNIT** (opcional): Preço unitário do produto

### ⚙️ Observações Importantes

1. **Nomes das colunas flexíveis**: O sistema aceita variações como:
   - `codigo`, `código`, `code`, `item`
   - `descricao`, `descrição`, `description`, `produto`
   - `unid`, `unidade`, `un`, `unit`
   - `VALOR UNIT`, `valor unitário`, `preco`, `preço`, `price`

2. **Formato do preço**: Aceita múltiplos formatos:
   - `17,00` ou `17.00` (número)
   - `R$ 17,00` (com símbolo)
   - `17` (sem centavos)

3. **Primeira aba**: O sistema lê automaticamente a primeira aba (sheet) da planilha

4. **Sem cabeçalho repetido**: Use apenas uma linha de cabeçalho

## 🚀 Como Usar

### 1️⃣ Carregar Tabela de Preços
1. Clique em **"Carregar Planilha Excel"**
2. Selecione seu arquivo `.xlsx`
3. Aguarde a confirmação (mostra quantidade de produtos carregados)

### 2️⃣ Preencher Dados do Pedido
1. Digite o **nome do cliente**
2. Ajuste a **data de abertura** (já vem com a data de hoje)

### 3️⃣ Adicionar Itens
1. Digite o **código do produto** no campo
2. Clique em **"Buscar"** (ou pressione Enter)
3. O sistema preenche automaticamente:
   - Descrição
   - Unidade
   - Valor unitário
4. Informe a **quantidade**
5. Clique em **"Adicionar ao Pedido"**

### 4️⃣ Visualizar e Imprimir
1. Clique em **"Visualizar e Imprimir"**
2. Confira os dados na tela
3. Clique em **"🖨️ Imprimir / Salvar PDF"**
4. Escolha sua impressora ou **"Salvar como PDF"**

## 📱 Compatibilidade

- ✅ **Desktop**: Chrome, Firefox, Edge, Safari
- ✅ **Mobile**: Android (Chrome) e iOS (Safari)
- ✅ **Impressoras**: Qualquer impressora compatível com o navegador
- ✅ **PDF**: Salvar como PDF em todos os navegadores

## 💾 Armazenamento de Dados

### O que é salvo no localStorage?
- Tabela de preços importada
- Cliente e data do pedido atual
- Itens adicionados ao pedido
- Dados persistem ao atualizar ou fechar a página

### Como limpar os dados?
- Use o botão **"Limpar Tudo"** para reiniciar o pedido
- Para limpar a tabela de preços, recarregue um novo arquivo Excel

## 🎨 Personalização

### Alterar Dados da Empresa
Edite o arquivo `print.html`:

```html
<!-- Linha 23-29: Informações da empresa -->
<p class="company-cnpj">CNPJ: 00.000.000/0001-00</p>
<p class="company-name">SUA EMPRESA LTDA</p>
<p class="company-address">ENDEREÇO COMPLETO DA SUA EMPRESA</p>
<p class="company-bank">BANCO: Agência: 0000-0 Conta: 000000-0</p>
<p class="company-contact">CONTATO: (00) 00000-0000</p>
<p class="company-email">contato@empresa.com</p>

<!-- Linha 91-95: Rodapé -->
<p class="footer-company">SUA EMPRESA DISTRIBUIDORA LTDA</p>
<p class="footer-cnpj">CNPJ da empresa: 00.000.000/0001-00</p>
<p class="footer-name">NOME DO RESPONSÁVEL</p>
<p class="footer-cpf">CPF: 000.000.000-00</p>
```

### Adicionar Logo da Empresa
Substitua a `div.logo-placeholder` (linha 20-22) por:

```html
<div class="logo-area">
    <img src="imagens/sua-logo.png" alt="Logo" style="max-width: 40mm; max-height: 20mm;">
</div>
```

## 🗂️ Estrutura de Arquivos

```
├── index.html          # Página de boas-vindas (ABRIR ESTA)
├── sistema.html        # Página principal do sistema (cadastro)
├── print.html          # Página de impressão (A4)
├── gerar-exemplo.html  # Gera planilha de teste
├── ajuda-planilha.html # Tutorial da planilha Excel
├── README.md           # Documentação completa
├── INICIO-RAPIDO.md    # Guia rápido
├── css/
│   ├── style.css       # Estilos da página principal
│   └── print.css       # Estilos de impressão A4
└── js/
    ├── app.js          # Lógica principal e importação Excel
    └── print.js        # Lógica da página de impressão
```

## 🔧 Tecnologias Utilizadas

- **HTML5**: Estrutura semântica
- **CSS3**: Layout responsivo e estilos de impressão `@media print`
- **JavaScript (ES6)**: Lógica da aplicação
- **SheetJS (xlsx)**: Biblioteca para leitura de arquivos Excel
- **localStorage**: Persistência de dados no navegador
- **Font Awesome**: Ícones

## ❌ Funcionalidades Não Implementadas

- Backend/servidor (tudo funciona no navegador)
- Banco de dados remoto
- Autenticação de usuários
- Histórico de pedidos anteriores
- Edição de itens após adicionar (apenas remoção)
- Múltiplas tabelas de preços simultâneas

## 🎯 Próximos Passos Recomendados

1. **Histórico de pedidos**: Salvar pedidos finalizados e permitir consulta
2. **Edição de itens**: Permitir editar quantidade/preço após adicionar
3. **Múltiplos clientes**: Cadastro de clientes frequentes
4. **Observações**: Campo para adicionar observações no pedido
5. **Assinatura digital**: Campo para assinatura do cliente
6. **Envio por e-mail**: Integração para enviar recibo por e-mail
7. **QR Code**: Gerar QR Code para validação do recibo
8. **Temas**: Opção de trocar cores e layout

## 📞 Suporte

Para problemas ou dúvidas:
1. Verifique se a planilha Excel está no formato correto
2. Confira se o navegador está atualizado
3. Teste em modo anônimo (para descartar extensões)
4. Limpe o cache do navegador se houver problemas

## 🔒 Privacidade

- Todos os dados ficam armazenados **localmente no seu navegador**
- Nenhum dado é enviado para servidores externos
- A planilha Excel é processada inteiramente no navegador
- Você tem controle total sobre seus dados

---

**Versão**: 1.0.0  
**Data**: Fevereiro 2026  
**Tipo**: Progressive Web App (PWA) - Estático
