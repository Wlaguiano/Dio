# 🔐 Projeto de Pentest: Ataques de Força Bruta com Kali Linux e Medusa

## 📋 Descrição do Projeto

Este projeto documenta a implementação prática de ataques simulados de força bruta utilizando **Kali Linux** e **Medusa** em ambientes vulneráveis controlados (**Metasploitable 2** e **DVWA**). O objetivo é demonstrar técnicas de pentest, identificar vulnerabilidades comuns e propor medidas de mitigação.

---

## ⚠️ Aviso Legal

**Este projeto é exclusivamente para fins educacionais e deve ser realizado apenas em ambientes controlados e autorizados.**

- ✅ Use apenas em VMs locais (host-only network)
- ✅ Nunca execute ataques em sistemas sem autorização explícita
- ❌ Ataques não autorizados são **crimes** previstos em lei

---

## 🎯 Objetivos de Aprendizagem

Ao concluir este projeto, você será capaz de:

- ✅ Compreender ataques de força bruta em diferentes serviços (FTP, Web, SMB)
- ✅ Utilizar o **Kali Linux** e o **Medusa** para auditoria de segurança
- ✅ Documentar processos técnicos de forma clara e estruturada
- ✅ Reconhecer vulnerabilidades comuns e propor medidas de mitigação
- ✅ Utilizar o GitHub como portfólio técnico

---

## 🛠️ Ferramentas Utilizadas

| Ferramenta | Versão | Descrição |
|------------|--------|-----------|
| **Kali Linux** | 2024.4 | Sistema operacional para pentest |
| **Medusa** | 2.2 | Ferramenta de força bruta paralela |
| **Metasploitable 2** | - | Máquina vulnerável para testes |
| **DVWA** | 1.10 | Aplicação web vulnerável |
| **VirtualBox** | 7.0+ | Virtualização |
| **Nmap** | 7.94 | Scanner de rede |

---

## 🏗️ Arquitetura do Ambiente

```
┌─────────────────────────────────────────────┐
│           VirtualBox (Host-Only)            │
│                                             │
│  ┌──────────────┐        ┌───────────────┐ │
│  │  Kali Linux  │───────▶│ Metasploitable│ │
│  │  (Atacante)  │        │   2 (Alvo)    │ │
│  │ 192.168.56.X │        │ 192.168.56.Y  │ │
│  └──────────────┘        └───────────────┘ │
│         │                                   │
│         │                                   │
│         └──────────────▶┌────────────────┐ │
│                         │   DVWA (Alvo)  │ │
│                         │ 192.168.56.Z   │ │
│                         └────────────────┘ │
└─────────────────────────────────────────────┘
```

---

## 📁 Estrutura do Repositório

```
pentest-project/
├── README.md                          # Este arquivo
├── docs/
│   ├── 01-configuracao-ambiente.md    # Setup das VMs
│   ├── 02-ataque-ftp.md               # Brute force FTP
│   ├── 03-ataque-dvwa.md              # Ataque Web (DVWA)
│   ├── 04-ataque-smb.md               # Password spraying SMB
│   └── 05-mitigacoes.md               # Recomendações de segurança
├── wordlists/
│   ├── usuarios.txt                   # Lista de usuários
│   └── senhas.txt                     # Lista de senhas
├── scripts/
│   ├── scan-rede.sh                   # Script de reconhecimento
│   └── ataque-automatizado.sh         # Automação Medusa
└── images/
    ├── ambiente-virtualbox.png
    ├── ataque-ftp-sucesso.png
    └── dvwa-explorado.png
```

---

## 🚀 Como Executar o Projeto

### Pré-requisitos

- VirtualBox instalado
- ISO do Kali Linux baixada
- Metasploitable 2 OVA baixada
- DVWA configurada (pode ser em Docker)
- Conhecimentos básicos de Linux e redes

### Passo a Passo

1. **Clone este repositório:**
```bash
git clone https://github.com/seu-usuario/pentest-project.git
cd pentest-project
```

2. **Configure o ambiente:**
- Siga o guia em [`docs/01-configuracao-ambiente.md`](docs/01-configuracao-ambiente.md)

3. **Execute os ataques simulados:**
- FTP: [`docs/02-ataque-ftp.md`](docs/02-ataque-ftp.md)
- DVWA: [`docs/03-ataque-dvwa.md`](docs/03-ataque-dvwa.md)
- SMB: [`docs/04-ataque-smb.md`](docs/04-ataque-smb.md)

4. **Documente seus resultados:**
- Adicione capturas de tela em `images/`
- Descreva suas observações em cada arquivo `.md`

---

## 📊 Resultados Esperados

Após completar os ataques simulados, você deverá ter:

- ✅ Acesso obtido via FTP com credenciais fracas
- ✅ Exploração de formulário web vulnerável (DVWA)
- ✅ Enumeração de usuários via SMB
- ✅ Documentação completa com capturas de tela
- ✅ Lista de vulnerabilidades encontradas
- ✅ Recomendações de mitigação implementáveis

---

## 🔒 Vulnerabilidades Identificadas

| Serviço | Vulnerabilidade | Gravidade | Mitigação |
|---------|-----------------|-----------|-----------|
| FTP | Senha padrão "msfadmin" | CRÍTICA | Política de senhas fortes |
| DVWA | SQL Injection | ALTA | Input validation + prepared statements |
| SMB | User enumeration | MÉDIA | Restringir acesso anônimo |
| SSH | Tentativa de brute force | ALTA | Fail2ban + chave SSH |

---

## 📚 Referências e Documentação

### Documentação Oficial
- [Kali Linux – Site Oficial](https://www.kali.org/)
- [Medusa – Documentação](http://foofus.net/goons/jmk/medusa/medusa.html)
- [DVWA – Damn Vulnerable Web Application](https://dvwa.co.uk/)
- [Metasploitable 2 – Guia](https://docs.rapid7.com/metasploit/metasploitable-2/)
- [Nmap – Manual Oficial](https://nmap.org/book/man.html)

### Materiais Complementares
- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [MITRE ATT&CK Framework](https://attack.mitre.org/)
- [Guia de Markdown do GitHub](https://guides.github.com/features/mastering-markdown/)

---

## 🤝 Contribuições

Contribuições são bem-vindas! Se você:

- Encontrou um erro na documentação
- Quer adicionar novos cenários de ataque
- Tem sugestões de melhoria

**Faça um fork e abra um Pull Request!**

---
## 📝 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---

## 🎓 Status do Projeto

- [x] Configuração do ambiente
- [x] Ataque FTP com Medusa
- [x] Ataque DVWA (formulário web)
- [x] Password spraying SMB
- [x] Documentação completa
- [x] Capturas de tela
- [ ] Vídeo demonstrativo (opcional)

---

**Bons estudos e lembre-se: use o conhecimento de forma ética! 🛡️**
