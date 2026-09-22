# Teste técnico — Dev Sênior

## O problema

Uma plataforma de agendamento para salões de beleza, no estilo iFood: vários salões se cadastram, cada um com seus próprios profissionais, serviços e horários

* Cada salão tem seus profissionais, seu catálogo de serviços e seus horários de funcionamento.
* Cada profissional tem seus próprios dias e horários de trabalho e realiza um subconjunto dos serviços do salão.
* Cada serviço possui uma duração definida, como 30 min, 1h, 1h30 etc.
* O cliente escolhe:
  * salão;
  * serviço;
  * profissional ou **"sem preferência"**;
  * dia;
  * horário.
* Após o agendamento, o cliente recebe a confirmação.
* Dois clientes nunca podem ficar com horários conflitantes para o mesmo profissional, mesmo que tentem agendar simultaneamente.
* O cliente pode cancelar um agendamento.
* Cancelamentos realizados com menos de 2 horas de antecedência devem gerar uma taxa.
* Duas horas antes do atendimento, o cliente deve receber um lembrete por WhatsApp. O envio pode ser simulado, registrando a tentativa em log ou tabela no banco.
* Cada salão precisa visualizar a própria agenda do dia separada por profissional.

Para o teste, basta popular a base com 2 ou 3 salões de exemplo. O que importa é que a modelagem e as regras suportem N salões.

O sistema será tratado como uma aplicação que poderia ir para produção: deve subir com Docker, possuir pipeline de CI/CD utilizando GitHub Actions e ficar atrás de um nginx.


## Stack obrigatória
* **Frontend:** React com **Next.js**
* **Backend:** Node.js com **NestJS**
* **ORM:** **Prisma**
* **Banco de dados:** PostgreSQL
* **Containers:** Docker / Docker Compose
* **CI/CD:** GitHub Actions
* **Proxy reverso:** nginx *(desejável, não obrigatório)*


## Regras
* **IA é liberada**
* Prazo: **3 dias corridos a partir do recebimento**.
* A entrega deve ser feita em um repositório Git privado, com acesso liberado para **tecnologia@glossexpress.com**.
* Esperamos que o repositório tenha um **histórico real de commits**


## O que entregar

### 1. Repositório
* sobe com `docker compose up` (app, banco e o que mais precisar);
* seed com 2 ou 3 salões de exemplo;
* testes — pelo menos um que prove que dois clientes **simultâneos** não conseguem o mesmo horário com o mesmo profissional.

### 2. Pipeline no GitHub Actions
* instale as dependências;
* rode os testes;
* faça o build da aplicação;
* publique a imagem Docker no **GHCR** (registry do próprio GitHub, `ghcr.io`).


### 3. Vídeo de até 5 minutos

Grave um vídeo explicando as decisões técnicas e arquiteturais que você tomou e **por que** tomou cada uma.

* o que você escolheu;
* quais alternativas considerou;
* por que escolheu essa abordagem;
* quais trade-offs existem;
* o que pode quebrar caso essa decisão esteja errada.

No final do vídeo, responda:

1. O que quebra primeiro se o volume subir **10×**?
2. O que você cortou por falta de tempo?
3. O que a IA sugeriu e você decidiu **não usar**?

## Como avaliamos

Queremos avaliar principalmente **como você toma essas decisões e quais trade-offs considera**.

Não estamos procurando quantidade de código ou complexidade desnecessária. Estamos procurando **boas decisões de engenharia, domínio da stack e capacidade de identificar riscos reais de produção**.

## Entrega

Envie:

* link do repositório;
* link do vídeo.

Para: tecnologia@glossexpress.com