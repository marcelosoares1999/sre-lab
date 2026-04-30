printf '%s\n' \
'# P1: Nginx Inativo | 29/04/2026' \
'' \
'## 1. Detecção' \
'Sintoma: curl localhost:80 connection refused' \
'Impacto: 100% indisponibilidade do serviço web' \
'Horário: 06:20' \
'' \
'## 2. Diagnóstico' \
'bash' \
'sudo systemctl status nginx' \
'# Resultado: inactive (dead)' \
'' \
'Causa raiz: Serviço nginx não habilitado para iniciar com o sistema.' \
'' \
'## 3. Mitigação' \
'bash' \
'sudo systemctl start nginx' \
'sudo systemctl enable nginx' \
'' \
'' \
'## 4. Validação' \
'bash' \
'curl -I localhost' \
'# HTTP/1.1 200 OK' \
'systemctl is-active nginx' \
'# active' \
'' \
'' \
'## 5. Prevenção' \
'Executar sudo systemctl enable nginx em toda nova instalação para garantir persistência após reboot.' \
'' \
'*MTTR: 2min*' \
'*Comando chave:* systemctl enable nginx' \
> dia-01-nginx-inativo.md
