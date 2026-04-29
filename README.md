# SRE Lab - Treinamento P1/P0 com Evidências | Joao Marcelo Soares Siqueira

*Objetivo*: Migrar de Suporte N1 para SRE N2 em 30 dias documentados.  
*Stack*: Linux, Docker, Nginx, Python, Prometheus, GitHub Actions  
*SLA Pessoal*: Disponibilidade 06:00-06:48 BRT, MTTR <15min  

## Métricas do Lab
| Dia | Incidente | MTTR | Status | Artefato |
| --- | --- | --- |
| 0 | Setup Ubuntu + Git | - | OK | Commit inicial |
| 1 | P1: Nginx Down | 2min | OK | [Runbook](./runbooks/nginx-down.md) |
| 2 | A definir | - | Pendente | - |

## Filosofia SRE
1. *SLI > Ego*: Se não mede, não existe
2. *Runbook > Memória*: Incidente sem doc = dívida técnica  
3. *MTTR < 15min*: Tudo acima disso é P0
## Como Validar
```bash
git clone https://github.com/marcelosoares1999/sre-lab.git
cd sre-lab
git log --oneline  # Prova de execução diária
