# P1: Nginx Down - Sev2 | 29/04/2026

## 1. Alerta
*Sintoma*: curl localhost:80 connection refused
*Impacto*: 100% usuários fora
*Detecção*: 06:20
*MTTR*: 2min

## 2. Diagnóstico
```bash
sudo systemctl status nginx  # inactive dead
