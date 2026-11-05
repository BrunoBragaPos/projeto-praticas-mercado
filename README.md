# Projeto Aplicado: Práticas de Mercado

## Autor

**Bruno Braga**  
**E-mail Institucional:** bruno.braga@uab.uncisal.edu.br

---

# Descrição do Projeto

Este projeto foi desenvolvido para a disciplina **Projeto Aplicado: Práticas de Mercado**, com o objetivo de implementar uma aplicação Web segura utilizando computação em nuvem, práticas de DevOps, versionamento de código e mecanismos básicos de segurança da informação.

O sistema foi desenvolvido utilizando o framework Laravel e implantado em uma infraestrutura Cloud AWS, atendendo aos requisitos definidos no escopo da disciplina.

---

# Ambiente de Produção

## Aplicação

**URL do Sistema**

https://brunopos.duckdns.org

## Repositório GitHub

https://github.com/BrunoBragaPos/projeto-praticas-mercado

---

# Tecnologias Utilizadas

## Infraestrutura

- AWS EC2
- Ubuntu Server
- Nginx
- PHP 8.5
- MariaDB
- Certbot
- Let's Encrypt
- DuckDNS
- Fail2Ban

## Desenvolvimento

- Laravel
- Laravel Breeze
- Blade Templates
- Vite
- Composer
- NodeJS

## DevOps

- Git
- GitHub
- GitHub Actions
- CI/CD
- Deploy Automatizado

---

# Funcionalidades Implementadas

## Login

O sistema possui autenticação de usuários utilizando Laravel Breeze.

## Dashboard

Após autenticação, o usuário é direcionado para uma área restrita protegida por middleware de autenticação.

## Logout

O usuário pode encerrar sua sessão de forma segura utilizando o recurso de logout.

---

# Arquitetura da Solução

```text
Internet
    │
    ▼
brunopos.duckdns.org
    │
    ▼
HTTPS
(Let's Encrypt)
    │
    ▼
Nginx
    │
    ▼
PHP 8.5
    │
    ▼
Laravel
    │
 ┌──┴──────┐
 │         │
 ▼         ▼
MariaDB   Sessões
```

---

# Infraestrutura Implantada

## Servidor

- AWS EC2
- Ubuntu Server

## DNS

Domínio configurado utilizando DuckDNS.

```text
brunopos.duckdns.org
```

## HTTPS

Foi implementado certificado SSL/TLS utilizando Let's Encrypt.

Todos os acessos HTTP são automaticamente redirecionados para HTTPS.

Exemplo:

```text
http://brunopos.duckdns.org
            ↓
https://brunopos.duckdns.org
```

---

# Segurança Implementada

## SSH por Chave

O acesso administrativo ao servidor é realizado utilizando autenticação por chave SSH.

Não são utilizadas senhas para administração da instância.

---

## Fail2Ban

Foi configurado o Fail2Ban para proteção contra ataques de força bruta na porta SSH.

Configuração aplicada:

```text
Máximo de tentativas: 4
Tempo de bloqueio: 24 horas
```

---

## HTTPS Obrigatório

Toda comunicação entre cliente e servidor ocorre utilizando criptografia TLS.

---

## Proteção de Sessão

As rotas protegidas utilizam middleware nativo do Laravel.

Usuários não autenticados são redirecionados automaticamente para a página de login.

---

# Versionamento de Código

O projeto utiliza Git para gerenciamento e controle de versões.

Principais práticas adotadas:

- Repositório público no GitHub
- Histórico de commits
- Controle de alterações
- Rastreamento de versões

---

# Integração Contínua e Entrega Contínua (CI/CD)

Foi implementada uma pipeline automática utilizando GitHub Actions.

Fluxo de funcionamento:

```text
Desenvolvedor
      │
      ▼
Git Commit
      │
      ▼
Git Push
      │
      ▼
GitHub
      │
      ▼
GitHub Actions
      │
      ▼
Deploy Automático
      │
      ▼
AWS EC2
```

A cada alteração enviada para a branch principal do projeto, o processo de deploy é executado automaticamente.

---

# OWASP Top 10

Durante o desenvolvimento foram implementadas medidas para mitigar vulnerabilidades previstas pela OWASP Top 10.

## A01 - Broken Access Control

Proteção de acesso às funcionalidades internas do sistema.

Implementação:

- Middleware de autenticação.
- Dashboard acessível apenas após login.

---

## A02 - Cryptographic Failures

Proteção contra falhas criptográficas.

Implementação:

- HTTPS obrigatório.
- Certificado SSL/TLS válido.
- Comunicação criptografada.

---

## A07 - Identification and Authentication Failures

Proteção dos mecanismos de autenticação.

Implementação:

- Laravel Breeze.
- Gestão de sessões.
- Logout seguro.
- Senhas armazenadas utilizando hash BCrypt.
- Proteção CSRF nativa do Laravel.

---

# Estrutura do Projeto

```text
app/
bootstrap/
config/
database/
public/
resources/
routes/
storage/
tests/

artisan
composer.json
composer.lock
package.json
vite.config.js
```

---

# Boas Práticas Aplicadas

- Infraestrutura em Cloud AWS
- HTTPS obrigatório
- Certificado SSL válido
- Bloqueio de força bruta com Fail2Ban
- Controle de acesso
- Proteção CSRF
- Deploy automatizado
- Versionamento Git
- Repositório GitHub
- Utilização de .gitignore
- Exclusão de credenciais do repositório

---

# Evidências de Implementação

## Infraestrutura

✅ AWS EC2

✅ Ubuntu Server

✅ Swap configurada

✅ Nginx

✅ PHP 8.5

✅ MariaDB

✅ HTTPS

✅ Certbot

✅ DuckDNS

✅ Fail2Ban

---

## Aplicação

✅ Laravel

✅ Login

✅ Dashboard

✅ Logout

✅ Middleware Auth

✅ Proteção CSRF

---

## DevOps

✅ Git

✅ GitHub

✅ GitHub Actions

✅ Deploy Automático

✅ CI/CD

---

# Conclusão

O projeto atende aos requisitos da disciplina Projeto Aplicado: Práticas de Mercado, contemplando infraestrutura em nuvem, autenticação de usuários, comunicação segura via HTTPS, proteção da camada de acesso ao servidor, versionamento de código e pipeline automatizada de integração e entrega contínua.

A solução desenvolvida segue princípios amplamente utilizados pelo mercado de tecnologia, demonstrando a aplicação prática de conceitos relacionados à computação em nuvem, DevOps, desenvolvimento Web e segurança da informação.
