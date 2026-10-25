# blackoutbot
BOT DE INTERAÇÃO PRO DISCORD

## Atualização cumulativa — 25/10/2026

O pacote inclui todas as alterações desde o SNAPSHOT original: administração e identidade, logs, Social, Jogos e eventos, Embed Maker V2, Mensagens enviadas, Cargos por reação e Central de segurança.

**[Abrir o ZIP completo SEM BANCO](atualizacoes/BLACKOUT-ATUALIZACAO-COMPLETA-SEM-BANCO-25-10-2026.zip)** — abra o arquivo e use o botão de download do GitHub (Download raw file).

**Não use Code → Download ZIP como pacote para a Square Cloud.** Esse botão baixa o repositório, com o pacote de atualização dentro. O arquivo a aplicar é o ZIP nomeado acima, que já possui app/, src/, assets/ e prisma/ na raiz.

Leia [as instruções antes de atualizar](atualizacoes/LEIA-ANTES-DE-UPAR-BLACKOUT.md).

- O pacote não contém banco, .env, arquivos auxiliares SQLite ou backups.
- Aplique sobre a mesma aplicação, mantendo arquivos ausentes do ZIP. Não limpe/recrie o projeto.
- Preserve o banco atual, a DATABASE_URL, o ambiente e migrations anteriores. Guarde o snapshot atual.
- As migrations acrescentam estrutura; o preenchimento de pontuação do TERMO afeta somente um campo novo. Não apagam registros nem reescrevem colunas antigas.
- Código validado com 319 testes offline. Não houve deploy ou acesso ao banco atual da Square Cloud. A validação SQL foi feita numa cópia do banco enviado anteriormente.

SHA-256: `812ec636f82ca41df324785011eb4841687dcb0766c90015481a87db2c02057b`.
