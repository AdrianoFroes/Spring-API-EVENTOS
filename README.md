Fluxograma da Aplicação
A aplicação segue o padrão MVC, onde as requisições HTTP são tratadas pelos Controllers, que realizam validações e acessam os Repositories responsáveis pela persistência no banco de dados.

Fluxo Geral da API
Cliente → Controller → Repository → Banco de Dados → Resposta HTTP

Fluxo – Cadastro de Evento
Cliente realiza requisição POST.
Controller valida os dados.
Evento é salvo no banco de dados.
Retorna HTTP 201 (Created).
Fluxo – Listagem de Eventos
Cliente realiza requisição GET.
Controller consulta o banco.
Retorna lista de eventos com HTTP 200 (OK).
Fluxo – Cadastro de Convidado
Cliente envia requisição POST para um evento específico.
Sistema verifica se o evento existe.
Convidado é salvo no banco.
Retorna HTTP 201 (Created).
Fluxo Geral da API
(Início) ↓ POST /eventos ↓ EventoController ↓ Validação dos dados ↓ Dados válidos? ├── Não → Retorna 400 Bad Request └── Sim ↓ EventoRepository.save() ↓ Banco de Dados ↓ Retorna 201 Created ↓ (Fim)
