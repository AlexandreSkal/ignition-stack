Execute operações no MongoDB. Comando: $ARGUMENTS

Exemplos de uso:
- `/db show databases` - lista bancos
- `/db show collections` - lista coleções do banco brewery
- `/db query <collection>` - mostra documentos de uma coleção
- `/db stats` - estatísticas do banco

Use `docker exec` para rodar comandos mongosh:
```bash
docker exec ignition-mongodb mongosh -u ignition -p --authenticationDatabase admin --quiet --eval '<comando>'
```

IMPORTANTE: Para a senha, leia do arquivo .env a variável MONGO_ROOT_PASSWORD.

Se nenhum argumento foi passado, mostre as opções disponíveis.
