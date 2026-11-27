# Notas – Aula 12 (TF 12)

## Inicialização automática (`user_data.sh`)
- Script de entrada em `terraform/modules/compute/user_data.sh` configurado para instalar Docker / Docker Compose e subir os contêineres do Moodle automaticamente no boot da instância EC2.

## Segurança (`.env` e IMDSv2)
- Permissões do arquivo `.env` restritas localmente e mantidas fora do Git (`.gitignore`).
- Exigência de `IMDSv2` (`http_tokens = "required"`) configurada nas opções de metadados da instância EC2.

## Módulos Terraform e regra do RDS
- Revisada a integração de `outputs` e `inputs` entre os módulos `networking`, `compute` e `database` (respeitando as restrições do AWS Learn Lab).
- Security Group do RDS PostgreSQL configurado para aceitar conexões (porta `5432`) apenas a partir do Security Group da instância EC2, com acesso público desabilitado.

## Testes e Docker Compose
- Suíte de testes automatizados executada com **66 testes aprovados**.
- Validação da configuração dos dois arquivos Docker Compose concluída.

## Versionamento
- Alterações commitadas e enviadas (`push`) para o fork do repositório `implement_Moodle` no GitHub.