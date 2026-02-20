# 🚀 INÍCIO RÁPIDO

## 📝 Passo a Passo para Começar

### 1. Preparar sua Planilha Excel
Crie um arquivo Excel (.xlsx) com estas colunas:

```
| codigo | descricao              | unid    | VALOR UNIT |
|--------|------------------------|---------|------------|
| 001    | TOCA SANFONADA        | PCT/100 | 17,00      |
| 002    | LUVA CIRURGICA        | CX      | 87,00      |
```

**OU** use o arquivo de exemplo:
- Abra `gerar-exemplo.html` no navegador
- Clique em "Gerar e Baixar Planilha"
- Use o arquivo baixado

### 2. Usar o Sistema

1. **Abra** `sistema.html` no navegador
2. **Carregue** sua planilha Excel
3. **Preencha** cliente e data
4. **Digite** o código do produto
5. **Clique** "Buscar" (os dados aparecem automaticamente)
6. **Informe** a quantidade
7. **Adicione** ao pedido
8. **Repita** para mais itens
9. **Clique** "Visualizar e Imprimir"
10. **Imprima** ou salve como PDF

## 🎯 Códigos de Exemplo

Se usar a planilha de exemplo:
- `001` - TOCA SANFONADA
- `002` - LUVA CIRURGICA
- `003` - MASCARA N95
- `004` - ALCOOL GEL 70%
- `005` - SERINGA 10ML

## ⚙️ Personalizar para sua Empresa

Edite o arquivo `print.html` (linhas 23-29 e 91-95):

```html
<!-- Trocar dados da empresa -->
<p class="company-cnpj">CNPJ: SEU_CNPJ</p>
<p class="company-name">SUA EMPRESA LTDA</p>
<p class="company-address">SEU ENDEREÇO</p>
<p class="company-bank">BANCO: Agência: XXXX-X Conta: XXXXX-X</p>
<p class="company-contact">CONTATO: (XX) XXXXX-XXXX</p>
<p class="company-email">seuemail@empresa.com</p>
```

## 🖼️ Adicionar seu Logo

Substitua no `print.html` (linha 20-22):

```html
<div class="logo-area">
    <img src="sua-logo.png" alt="Logo" style="max-width: 40mm;">
</div>
```

## ❓ Problemas Comuns

**Produto não encontrado?**
- Verifique se o código está correto
- Confira se a planilha foi carregada
- Códigos são case-insensitive (001 = 001)

**Tabela não carrega?**
- Use arquivo .xlsx (não .xls ou .csv)
- Verifique se tem as colunas corretas
- Primeira linha deve ser o cabeçalho

**Não imprime direito?**
- Use Chrome/Edge (melhores resultados)
- Na impressão, escolha "Retrato" e A4
- Desmarque "Cabeçalhos e rodapés"

## 📁 Arquivos do Sistema

```
├── index.html           ← Página de boas-vindas (ABRIR ESTA)
├── sistema.html         ← Sistema principal
├── print.html           ← Página de impressão
├── gerar-exemplo.html   ← Gera planilha de teste
├── README.md            ← Documentação completa
├── INICIO-RAPIDO.md     ← Este arquivo
├── css/
│   ├── style.css
│   └── print.css
└── js/
    ├── app.js
    └── print.js
```

## 💡 Dicas

✅ **Ctrl+P** na tela de impressão para imprimir rápido  
✅ **Enter** no campo código para buscar  
✅ Dados salvos automaticamente (não perde ao atualizar)  
✅ Funciona offline depois de abrir uma vez  
✅ Funciona no celular também  

---

**🎉 Pronto! Agora é só começar a usar!**
