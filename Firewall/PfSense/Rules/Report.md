# Relatório de Regras de Firewall – Interface OPT1

## 📌 Visão Geral
![Visão Geral](https://github.com/Juliocesar-sec/Firewall/blob/72ed2d1c03fec8cb2e3c594484708d85fae901af/PfSense/Rules/Screenshot/Screenshot_2026-04-26_16-42-06.png)

Este relatório descreve a configuração de regras de firewall aplicadas à interface **OPT1**, com foco na segurança e controle de tráfego de rede.

A análise foi realizada com base nas portas e protocolos atualmente permitidos e nas boas práticas de segurança de redes.

---

## 🔓 Regras de Tráfego Permitidas (OPT1 → qualquer destino)

Atualmente, a rede OPT1 permite os seguintes serviços:

- DNS (porta 53 TCP/UDP)
- HTTP (porta 80 TCP) *(opcional)*
- HTTPS (porta 443 TCP)
- ICMP (ping entre hosts da rede OPT1)

---

## 🔒 Regras de Segurança Recomendadas

Para melhorar a segurança da rede, recomenda-se a seguinte política:

### ✔️ Manter permitido
- DNS (53 TCP/UDP)
- HTTPS (443 TCP)
- HTTP (80 TCP) *(apenas se necessário)*

### ❌ Bloquear (na maioria dos cenários)
- Telnet (23 TCP) → comunicação não criptografada
- FTP (21 TCP) → transferência de arquivos sem segurança
- SMTP (25 TCP) → potencial uso indevido para envio de spam
- VNC (5900 TCP) → acesso remoto com alto risco de exposição

### ⚙️ SSH (22 TCP)
- Deve ser mantido apenas se houver necessidade administrativa na rede OPT1
- Recomenda-se restringir o acesso por endereço IP de origem confiável
- Preferencialmente utilizar autenticação por chave em vez de senha

---

## 🛡️ Conclusão

A aplicação das regras propostas reduz significativamente a superfície de ataque da rede OPT1, eliminando protocolos inseguros e limitando o tráfego apenas ao necessário.

Isso melhora a postura de segurança da rede, reduz riscos de exploração e facilita o controle de acessos.


