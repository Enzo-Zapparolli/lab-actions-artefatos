# GitHub Actions — artefatos e gatilhos

**Laboratório educacional de automação de workflows.** Demonstra a geração de arquivos em um job e a recuperação dos artefatos em outro.

[Portfólio](https://github.com/Enzo-Zapparolli) · [Workflow](.github/workflows/pipeline-inteligente.yml)

## Fluxo

1. `job_gerador` cria dois arquivos de relatório de demonstração.
2. `actions/upload-artifact` publica os arquivos como artefato da execução.
3. `job_auditoria`, dependente do primeiro job, baixa e lista os arquivos.

## Gatilhos definidos

- Execução manual em **Actions → Pipeline Inteligente com Artefatos → Run workflow**.
- Agendamento cron `0 2 * * *` (UTC).
- Push em branches `feature/**`, com mudanças em `src/**`, excluindo `src/docs/**`.

O cron está definido no YAML; disponibilidade do agendamento e estado das execuções devem ser consultados na aba Actions.

## Escopo

Os relatórios são textos simulados. `testes/suite.test.js` é um marcador textual e não uma suíte de testes executável. O workflow não testa a aplicação; seu foco é demonstrar artefatos, filtros de execução e dependência entre jobs.
