name: Como usar variavel de ambiente e contexto do GitHub Actions
on: 
  workflow_dispatch: 
env:
  ENV_WORKFLOW: "Valor WORKFLOW"
jobs:
  contextos:
    runs-on: ubuntu-latest
    env:
        ENV_JOB: "Valor JOB CONTEXT"
    steps:
      - name: Contexto github
        env:
          GITHUB_CONTEXT: ${{ toJson(github) }}
        run: echo "$GITHUB_CONTEXT"
      - name: Contexto env
        env:
          ENV_CONTEXT: ${{ toJson(env) }}
        run: echo "$ENV_CONTEXT"
      - name: Contexto job
        env:
          JOB_CONTEXT: ${{ toJson(job) }}
        run: echo "$JOB_CONTEXT"
      - name: Contexto steps
        env:
          STEPS_CONTEXT: ${{ toJson(steps) }}
        run: echo "$STEPS_CONTEXT"
      - name: Contexto runner
        env:
          RUNNER_CONTEXT: ${{ toJson(runner) }}
        run: echo "$RUNNER_CONTEXT"
      - name: Contexto vars
        env:
          RUNNER_VARS: ${{ toJson(vars) }}
        run: echo "$RUNNER_VARS"
      - name: Contexto vars
        run: echo "${{ vars.VARS_CONTEXT }}"
      - name: Contexto Secrets
        env:
          RUNNER_SECRETS: ${{ toJson(secrets) }}
        run: echo "$RUNNER_SECRETS"
      - name: Variavel Secrets
        run: echo "${{ secrets.SECRETS_CONTEXT }}"
        
        - name: Contexto steps
          env:
            STEPS_CONTEXT: ${{ toJson(steps) }}
          run: echo "$STEPS_CONTEXT"
        
        - name: Contexto runner
          env:
            RUNNER_CONTEXT: ${{ toJson(runner) }}
          run: echo "$RUNNER_CONTEXT"
        
        - name: Contexto vars
          env:
            VARS_CONTEXT: ${{ toJson(vars) }}
          run: echo "$VARS_CONTEXT"
        
        - name: Contexto vars
          run: echo "${{ vars.VARS_CONTEXT }}"
