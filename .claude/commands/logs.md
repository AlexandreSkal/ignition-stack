Mostre os logs recentes da stack. O usuário pode especificar um serviço: $ARGUMENTS

Se nenhum serviço foi especificado, mostre as últimas 50 linhas de cada serviço:
- `docker logs --tail 50 ignition-gateway`
- `docker logs --tail 50 ignition-edge`
- `docker logs --tail 50 ignition-mongodb`

Se um serviço foi especificado (gateway, edge, mongodb, mongo-express), mostre as últimas 100 linhas desse serviço.

Mapeamento de nomes curtos:
- gateway → ignition-gateway
- edge → ignition-edge
- mongodb / mongo → ignition-mongodb
- express → mongo-express

Destaque erros (ERROR, Exception, WARN) encontrados nos logs.
