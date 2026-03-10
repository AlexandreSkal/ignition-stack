# Ignition Stack - IronForge Brewery

## Arquitetura

Stack SCADA/MES para cervejaria, rodando em Docker Compose.

### Serviços

| Container | Porta Host | Descrição |
|---|---|---|
| `ignition-gateway` | 8089 (http), 8044 (https) | Gateway principal - SCADA + MES |
| `ignition-edge` | 8088 (http), 8043 (https) | Edge Gateway - coleta de dados |
| `ignition-mongodb` | 27017 | MongoDB 7 - banco de dados |
| `mongo-express` | 8081 | UI web para MongoDB |

### Domínios (Traefik)

- `gateway.ironforge.beer` → ignition-gateway
- `edge.ironforge.beer` → ignition-edge
- `mongo.ironforge.beer` → mongo-express

### Rede

Todos os serviços usam a rede externa `automation-net`.

## Estrutura de arquivos

```
ignition-stack/
├── docker-compose.yml      # Compose principal
├── .env                    # Senhas e configs (NÃO committar)
├── .env.example            # Template de variáveis
├── edge-scripts/           # Scripts montados no Edge (/scripts)
├── gateway-scripts/        # Scripts montados no Gateway (/scripts)
├── gateway-backups/        # Backups .tar.gz (ignorado pelo git)
└── mongo-init/             # Scripts de inicialização do MongoDB
```

## Comandos úteis

```bash
# Subir a stack
docker compose up -d

# Parar a stack
docker compose down

# Ver logs de um serviço
docker logs -f ignition-gateway

# Entrar no container do gateway
docker exec -it ignition-gateway bash

# Status do Ignition
curl -s http://localhost:8089/StatusPing
```

## Regras para o Claude Code

- Sempre use variáveis do `.env` no docker-compose.yml, nunca senhas hardcoded
- Backups são grandes (>100MB) - nunca commitar no git
- O diretório de trabalho é `/home/ubuntu/ignition-stack`
- Para interagir com o Ignition, use `docker exec` ou a API REST na porta 8089
- Responder em português brasileiro
