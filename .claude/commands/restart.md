Reinicie a stack Ignition ou um serviço específico: $ARGUMENTS

Se nenhum serviço especificado:
1. Confirme com o usuário antes de reiniciar toda a stack
2. Execute `docker compose down && docker compose up -d`
3. Aguarde 30 segundos e verifique o status com `docker compose ps`

Se um serviço específico foi passado:
1. Execute `docker compose restart <serviço>`
2. Verifique o status após reiniciar

Mapeamento de nomes curtos:
- gateway → ignition-gateway
- edge → ignition-edge
- mongodb → mongodb
- express → mongo-express
