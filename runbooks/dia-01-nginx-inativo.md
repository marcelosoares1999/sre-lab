# P1: Nginx Inativo | 29/04/2026

## 1. Detecção
Sintoma: curl localhost:80 connection refused
Impacto: 100% indisponibilidade do serviço web
Horário: 06:20

## 2. Diagnóstico
```bash
sudo systemctl status nginx

 Resultado: inactive (dead)
```

## 3. Causa Raiz
Serviço não habilitado para iniciar com o boot.

## 4. Mitigação
```bash
sudo systemctl start nginx
sudo systemctl enable nginx
```
## 5. Prevenção
Criar check de systemctl is-enabled nginx.

## 6. Comando chave
```bash
systemctl enable nginx
```

## 7. Post-Mortem Blameless
*Resumo*: nginx offline após reboot 06:20. HTTP 502.
*Linha do tempo*: 06:20 Alerta → 06:21 Diagnóstico inactive → 06:22 Mitigação start+enable → 06:23 Validação 200 OK
*Causa raiz*: Serviço não habilitado no systemd.
*Ação preventiva*: Adicionar systemctl is-enabled nginx no checklist.

## 8. Evidência
*Antes:*
● nginx.service
   Loaded: loaded (/lib/systemd/system/nginx.service; disabled)
   Active: inactive (dead)
*Depois:*
● nginx.service
   Loaded: loaded (/lib/systemd/system/nginx.service; enabled)
   Active: active (running)

## 9. Sabotagem Controlada
```bash
sudo systemctl stop nginx && sudo systemctl disable nginx
