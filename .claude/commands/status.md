Verifique o status completo da stack Ignition:

1. Rode `docker compose ps` para ver o estado de todos os containers
2. Rode `docker compose ps --format json` para verificar health status
3. Teste o StatusPing do gateway: `curl -s http://localhost:8089/StatusPing`
4. Teste o StatusPing do edge: `curl -s http://localhost:8088/StatusPing`
5. Verifique uso de recursos: `docker stats --no-stream --format "table {{.Name}}\t{{.CPUPerc}}\t{{.MemUsage}}" ignition-gateway ignition-edge ignition-mongodb mongo-express`

Apresente um resumo claro com o estado de cada serviço.
