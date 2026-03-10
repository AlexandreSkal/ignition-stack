Faça deploy das alterações no docker-compose.yml:

1. Valide o compose: `docker compose config --quiet`
2. Se houver erros, mostre e pare
3. Mostre o diff das mudanças: `git diff docker-compose.yml`
4. Peça confirmação do usuário
5. Execute `docker compose up -d`
6. Aguarde 30 segundos e verifique o status de todos os containers
7. Se algum container não estiver healthy, mostre os logs dele
