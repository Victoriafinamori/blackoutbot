# BLACKOUT — Atualização completa SEM BANCO, 25/10/2026

Este ZIP reúne TODAS as alterações desde o SNAPSHOT original: navegação e PNGs BLACKOUT, personalização local, equipe/moderação, logs e destinos externos, registro/atendimento/comunidade, Social, Jogos e eventos, Embed Maker V2, Mensagens enviadas, Cargos por reação e Central de segurança.

É uma ATUALIZAÇÃO DE ARQUIVOS para a aplicação que já existe. Não é um projeto vazio para criar/recriar a aplicação. Arquivos de código com o mesmo caminho serão atualizados; banco e ambiente não estão no ZIP.

## Preservar os dados atuais

- Guarde o snapshot atual que você acabou de fazer, fora da aplicação.
- NÃO apague nem substitua `prisma/dev.db`, ou o banco indicado pela sua `DATABASE_URL` atual.
- NÃO altere a `DATABASE_URL` nem remova `.env`/variáveis de ambiente.
- Preserve todas as migrations anteriores já existentes na aplicação.
- Este ZIP NÃO contém banco, arquivos SQLite auxiliares, .env, backup, node_modules, dist, package.json, package-lock.json ou squarecloud.app. Ele mantém o código usado por app/index.js e a configuração existente de inicialização.

## Como aplicar

1. Pare temporariamente o bot antes de atualizar e mantenha o snapshot guardado.
2. Na MESMA aplicação da Square Cloud, use uma atualização de arquivos que mantenha os arquivos não incluídos no ZIP. Aplique os conteúdos na raiz do projeto, mantendo app/, src/, assets/ e prisma/ nas posições existentes.
3. NÃO exclua/recrie a aplicação e NÃO use opção que limpe ou substitua todos os arquivos. Se a tela anunciar que vai apagar arquivos ausentes do ZIP, cancele esse procedimento. A extração simples dos arquivos deste patch não escreve no banco; uma limpeza do projeto feita pela plataforma poderia apagá-lo.
4. Confira antes de iniciar: o banco original continua no caminho configurado, .env/variáveis continuam iguais e o MAIN continua app/index.js.
5. O START existente gera o Prisma Client e executa `prisma migrate deploy`. São seis migrations compatíveis com os dados existentes: criam tabelas/índices e acrescentam campos; uma também preenche a pontuação de partidas ganhas em um campo NOVO do TERMO. Não removem tabelas/colunas nem apagam registros existentes ou reescrevem valores das colunas antigas.
6. Inicie e confira os logs e os registros atuais do servidor antes de liberar o uso. Se uma migration falhar, NÃO use migrate reset, db push nem um banco vazio como solução. Pare e guarde o log para corrigir preservando o banco.

Não foi possível confirmar neste ambiente os rótulos ou o comportamento atual das telas de upload da Square Cloud. Esta entrega não afirma que qualquer método de envio de ZIP preserve arquivos: a atualização precisa manter os arquivos existentes.

## O que foi verificado

- Conteúdo original do pacote cumulativo validado pelo manifesto SHA-256 de cada arquivo.
- 319 testes offline aprovados, inclusive após aplicar o código sobre uma cópia sanitizada do SNAPSHOT.
- SQL das seis migrations verificado em uma cópia isolada do banco ENVIADO ANTERIORMENTE, preservando todas as colunas/valores das 123 tabelas originais. Essa cópia não é o banco atual da Square Cloud nem o snapshot que você acabou de fazer.
- Nenhum banco ou arquivo auxiliar SQLite incluído, inclusive por detecção do cabeçalho SQLite em arquivos sem extensão.
- Prisma validate e generate passaram; migrate deploy nativo e uso real no Discord não foram executados aqui. Existe um erro TypeScript anterior em denunciaSelects.ts:61, documentado nas entregas anteriores.

As 19 regras novas de segurança começam desligadas. Configure exceções e observação antes de ativar respostas. Os filtros antigos mantêm suas configurações independentes.

Guias incluídos: ATUALIZAR-SQUARE-CLOUD.md, SEGURANCA-BLACKOUT.md e MENSAGENS-E-CARGOS.md.

Não foi feito login, deploy, alteração ou restauração do banco vivo. O ZIP não sobrescreve o banco por conter outro arquivo de banco; a preservação também depende de aplicar a atualização sem apagar os arquivos existentes.
