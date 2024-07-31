# Projeto de Teste de Workflows do GitHub Actions

Este projeto foi criado para testar e verificar a funcionalidade de dois workflows do GitHub Actions. Esses workflows servem como exemplos de como automatizar tarefas de criação de tags e verificação de versões em arquivos `pubspec.yaml` para projetos Flutter.

## Workflows Adicionados

### 1. Verificação de Versão do Pubspec

Este workflow verifica se a versão especificada no `pubspec.yaml` já existe como uma tag no repositório quando uma Pull Request (PR) é aberta ou atualizada. Se a versão já existir, o workflow falhará, impedindo o merge da PR até que a versão seja incrementada.

**Arquivo do Workflow:** `.github/workflows/check-version.yml`

**Disparador:** Pull Request (`pull_request`)

**Passos Principais:**

- Extrai a versão do arquivo `pubspec.yaml`.
- Verifica se a tag correspondente à versão extraída já existe no repositório.
- Falha se a tag já existir, impedindo o merge da PR.

### 2. Criação Automática de Tag

Este workflow cria automaticamente uma tag baseada na versão especificada no `pubspec.yaml` sempre que uma alteração é mergeada na branch `main`. Isso ajuda a manter um controle de versão claro e organizado.

**Arquivo do Workflow:** `.github/workflows/tag-release.yml`

**Disparador:** Push na branch `main` (`push`)

**Passos Principais:**

- Extrai a versão do arquivo `pubspec.yaml`.
- Verifica se a tag correspondente à versão extraída já existe.
- Cria e push a nova tag se ela ainda não existir.

## Como Usar Esses Workflows em Outros Projetos

1. **Verificação de Versão do Pubspec:**

   - Copie o conteúdo do arquivo `.github/workflows/check-version.yml` para o repositório desejado.
   - Este workflow garantirá que a versão no `pubspec.yaml` seja única antes de permitir merges de PRs.

2. **Criação Automática de Tag:**
   - Copie o conteúdo do arquivo `.github/workflows/tag-release.yml` para o repositório desejado.
   - Este workflow automatizará a criação de tags baseadas na versão do `pubspec.yaml` sempre que houver um merge na branch `main`.

## Contribuição

Este projeto é um exemplo para demonstrar a utilização de workflows do GitHub Actions em projetos Flutter. Sinta-se à vontade para contribuir, sugerir melhorias ou adaptar os workflows para atender às suas necessidades específicas.

## Licença

Este projeto está licenciado sob os termos da [MIT License](LICENSE).
