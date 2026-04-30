# P1: Nginx Inativo | 29/04/2026

## 1. Detecção
Sintoma: curl localhost:80 connection refused
Impacto: 100% indisponibilidade do serviço web
Horário: 06:20

## 2. Diagnóstico
```bash
sudo systemctl status nginx

 Resultado: inactive (dead)

## 3. Causa Raiz
Serviço não habilitado para iniciar com o boot.

## 4. Mitigação
sudo systemctl start nginx
sudo systemctl enable nginx

## 5. Prevenção
Criar check de systemctl is-enabled nginx.

## 6. Comando chave
systemctl enable nginx
