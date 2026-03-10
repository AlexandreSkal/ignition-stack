Faça backup dos volumes Docker da stack Ignition.

Execute os seguintes passos:

1. Crie backups dos volumes Docker:
```bash
docker run --rm -v ignition-stack_ignition-gateway-data:/data -v $(pwd)/gateway-backups:/backup alpine tar czf /backup/ignition-gateway-data-backup-$(date +%Y%m%d-%H%M%S).tar.gz -C /data .
```

```bash
docker run --rm -v ignition-stack_ignition-edge-data:/data -v $(pwd)/gateway-backups:/backup alpine tar czf /backup/ignition-edge-data-backup-$(date +%Y%m%d-%H%M%S).tar.gz -C /data .
```

2. Liste os backups criados com tamanhos: `ls -lh gateway-backups/`
3. Informe o total de espaço usado pelos backups

IMPORTANTE: Pergunte ao usuário antes de deletar backups antigos.
