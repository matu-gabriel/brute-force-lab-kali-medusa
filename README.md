# 🔐 Simulação de Ataques de Força Bruta com Kali Linux e Medusa

## 📌 Descrição do Projeto

Este projeto tem como objetivo simular ataques de força bruta em um ambiente controlado, utilizando o Kali Linux e a ferramenta Medusa contra uma máquina vulnerável (Metasploitable 2).

A proposta é compreender como ataques de autenticação funcionam na prática, identificar vulnerabilidades e aplicar medidas de mitigação para fortalecer a segurança dos sistemas.

---

## 🎯 Objetivos

* Compreender ataques de força bruta em serviços reais (FTP, Web e SMB);
* Utilizar ferramentas de pentest como Medusa e Nmap;
* Documentar processos técnicos de forma clara e estruturada;
* Identificar vulnerabilidades e propor soluções de segurança;
* Criar um portfólio técnico no GitHub.

---

## 🧱 Ambiente de Testes

| Componente       | Descrição        |
| ---------------- | ---------------- |
| Sistema atacante | Kali Linux       |
| Sistema alvo     | Metasploitable 2 |
| Virtualização    | VirtualBox       |
| Rede             | Host-Only        |

---

## 🌐 Topologia da Rede

Kali Linux: 192.168.56.102
Metasploitable 2: 192.168.56.101

> ⚠️ Ambos conectados via rede Host-Only

---

## 🔍 Enumeração de Serviços

Antes dos ataques, foi realizado um scan utilizando o Nmap para identificar serviços ativos na máquina alvo.

### Comando utilizado:

```bash
nmap -sV 192.168.56.101
```

### Resultado:

* FTP (porta 21)
* SMB (porta 445)
* HTTP (porta 80)

---

## 💣 Ataques Realizados

---

### 🔓 Ataque 1 — Força Bruta em FTP

**Serviço:** FTP
**Porta:** 21
**Ferramenta:** Medusa

### Comando:

```bash
medusa -h 192.168.56.101 -u msfadmin -P wordlist.txt -M ftp
```

### Resultado:

* Credencial válida encontrada:

  * Usuário: msfadmin
  * Senha: msfadmin

### Validação:

Login realizado com sucesso via FTP.

---

### 🌐 Ataque 2 — Força Bruta em Aplicação Web (DVWA)

Foi utilizado um ambiente vulnerável (DVWA) para simular tentativas de login automatizadas.

### Processo:

* Identificação do formulário de login;
* Testes de múltiplas combinações de senha;
* Simulação de brute force.

### Resultado:

* Possível identificar falhas de proteção contra múltiplas tentativas de login.

---

### 🖥️ Ataque 3 — SMB Password Spraying

Foi realizada enumeração de usuários e tentativa de autenticação em massa (password spraying).

### Objetivo:

* Testar senhas comuns contra múltiplos usuários;
* Identificar contas com credenciais fracas.

---

## 🧪 Wordlists Utilizadas

* Wordlist simples para testes básicos;
* Possibilidade de uso da rockyou.txt (Kali Linux);
* Criação de wordlist personalizada para simulação.

---

## 📸 Evidências

As evidências dos testes estão disponíveis na pasta `/images`.

Exemplos:

* Execução do Nmap
* Ataque com Medusa
* Login bem-sucedido

---

## 🛡️ Medidas de Mitigação

Com base nos testes realizados, as seguintes medidas são recomendadas:

* Implementar bloqueio após múltiplas tentativas de login;
* Utilizar autenticação multifator (MFA);
* Criar políticas de senhas fortes;
* Monitorar logs de autenticação;
* Desativar serviços desnecessários;
* Utilizar ferramentas de detecção de intrusão;
* Restringir acesso por IP quando possível.

---

## 📚 Aprendizados

Durante este projeto foi possível compreender:

* Como ataques de força bruta funcionam na prática;
* A importância de configurações seguras em serviços expostos;
* Como ferramentas como Medusa podem ser utilizadas em auditorias;
* A relevância da enumeração antes de qualquer ataque;
* A necessidade de boas práticas de segurança para evitar exploração.

---

## 🚀 Conclusão

Este projeto demonstrou que sistemas mal configurados e com credenciais fracas podem ser facilmente comprometidos através de ataques simples como brute force.

A prática reforça a importância da segurança preventiva e do uso de mecanismos de proteção adequados para evitar acessos não autorizados.

---

## ⚠️ Aviso Legal

Este projeto foi realizado exclusivamente para fins educacionais, em ambiente controlado e autorizado.
Qualquer uso indevido das técnicas apresentadas é de total responsabilidade do usuário.

---

## 👨‍💻 Autor

Desenvolvido por **Markyz0x**
