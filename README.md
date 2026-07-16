# Auto-Cadastral

Ferramenta de linha de comando para geração e consulta de situação cadastral de CPF e CNPJ.

## Funcionalidades

- **Geração de dados** — CPF, CNPJ, Pessoa completa (nome/RG/nascimento/email/celular) e Empresa (razão social/endereço/CEP/telefone)
- **Consulta CPF** — via API CPFHub (gratuita, 50 consultas/mês)
- **Consulta CNPJ** — via ReceitaWS (gratuito, sem key)
- **Filtros em lote** — validar CPFs, separar CNPJs ativos, consultar CPFs em arquivo
- **Geração em lote** — CPFs com opção de estado (UF)

## Dependências

```bash
pip install fordev requests
```

(Opcional para Selenium — experimental, bloqueado por Cloudflare)
```bash
pip install selenium
```

## Configuração

1. Acesse [app.cpfhub.io/auth/register](https://app.cpfhub.io/auth/register)
2. Crie conta gratuita (50 consultas grátis/mês)
3. Copie a API Key do dashboard
4. No menu do script: opção **7 - Configurar API Key**

## Uso

```bash
python3 autocadastral.py
```

### Menu principal

```
[1] Gerar CPF / CNPJ / Pessoa       — dados fictícios
[2] Consultar situação cadastral     — CPF ou CNPJ
[3] Filtrar CNPJs ativos (lote)      — lê arquivo, filtra ativos
[4] Filtrar CPFs válidos (lote)      — valida dígitos em lote
[5] Filtrar CPFs regulares (lote)    — consulta situação via API
[6] Gerar lote de CPFs               — gera N CPFs com UF
[7] Configurar API Key (CPFHub)
[8] Consultar CPFs do arquivo (lote) — consulta lote via CPFHub
[0] Sair
```

## APIs utilizadas

| Serviço | Finalidade | Limite |
|---------|-----------|--------|
| [CPFHub](https://app.cpfhub.io) | Consulta CPF (nome + situação) | 50/mês grátis |
| [ReceitaWS](https://receitaws.com.br) | Consulta CNPJ | 3/min |

## Licença

MIT
