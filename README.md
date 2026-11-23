# Autoriza OPME · Painel de Autorizações

Painel de pedidos, autorizações e cirurgias de OPME. Reúne o acompanhamento por vendedor, por médico e por hospital, os prazos em dias úteis, o histórico de preços por convênio, os logins dos portais e os relatórios em PDF.

- **Endereço:** https://guerra-lucas-96.github.io/Painel-Acompanhamento-Autoriza-es/
- **Site:** `index.html`, publicado no GitHub Pages (gratuito). Os ícones e o `manifest.webmanifest` permitem fixar o painel na tela do celular como um aplicativo.
- **Banco de dados:** Supabase, projeto `neurox-painel-opme` (plano gratuito, região São Paulo)

## Identidade visual

| Cor | Código | Uso |
|---|---|---|
| Azul-marinho profundo | `#17324D` | Textos, navegação e elementos de confiança |
| Verde-petróleo | `#2FB7A6` | Ações, aprovação e estados positivos |
| Amarelo-âmbar | `#F2B84B` | Destaques e pontos de atenção |
| Fundo claro | `#F4F7F8` | Base neutra das telas |

- **Tema:** o painel abre no tema claro. O botão de lua, no topo, alterna para o tema escuro.
- **Logo:** é desenhado em vetor dentro do próprio `index.html` (constantes `LOGO_PARTS` e `LOGO_WORD`). Clicar nele volta para a tela inicial.
- **Relógio:** fica no canto superior esquerdo, com data e hora.

## Como usar

1. **Cadastros:** cadastre vendedores, médicos, convênios e hospitais. Os hospitais de Aracaju já vêm cadastrados com CNPJ, e os feriados de 2026 e 2027 também.
2. **Novo processo:** informe paciente, vendedor, médico, convênio, hospital e data da solicitação. Em seguida, lance os itens cotados.
3. **Mover etapa:** o fluxo é Pedido → Cotação → Em análise → Autorizada → Agendada → Realizada, ou então Negada ou Cancelada.
4. **Valores autorizados:** preencha o valor unitário autorizado de cada item. Esses valores formam o histórico de preços por convênio.
5. **Processos:** filtre por vendedor, médico, convênio e hospital. O botão **PDF** gera o relatório exatamente da lista que está na tela.
6. **Relatórios:** escolha **por vendedor**, **por médico** ou **por hospital**. Para um nome específico sai um PDF. Para "todos", sai um PDF para cada um.
   - Todo PDF traz: paciente, médico, convênio, hospital, data da solicitação, tempo desde a solicitação até o dia do relatório e status.
   - **Vendedor:** resumo por médico e por hospital, e depois os pacientes divididos por médico e, dentro de cada médico, por hospital.
   - **Médico:** pacientes divididos por hospital.
   - **Hospital:** pacientes divididos por médico.
   - **Opções:** mostrar o valor autorizado, mostrar só as iniciais dos pacientes (LGPD) e escolher quais encerrados incluir.
   - **Diretoria:** relatório gerencial com indicadores, funil, rankings, tempos por etapa e prazos vencidos.
7. **Portais:** guarde o link, o usuário e a senha dos portais dos hospitais e operadoras. As senhas são criptografadas no aparelho com a **senha do cofre**. Se essa senha for esquecida, as senhas guardadas não têm como ser recuperadas.

## Dados de demonstração

Enquanto houver dados fictícios, aparece uma faixa amarela no topo do painel. Para começar de verdade, clique em **Apagar dados fictícios**. Só os exemplos são removidos.

## Prazos

- O prazo de referência é de **21 dias úteis** desde a solicitação, sem contar fins de semana nem feriados cadastrados.
- **Verde:** no prazo. **Âmbar:** a partir de 15 dias úteis. **Vermelho:** acima de 21 dias úteis.
- Os dois números podem ser ajustados em `PRAZO_DU` e `ALERTA_DU`, no bloco `CONFIGURAÇÃO` do `index.html`.

## No celular

Abra o endereço e use **Adicionar à Tela de Início** (no iPhone, pelo botão Compartilhar) ou **Adicionar à tela inicial** (no Android, pelo menu ⋮). Se o atalho já existia, apague-o e adicione de novo para ele pegar o ícone novo.

## Plano gratuito do Supabase

O projeto é pausado depois de 7 dias sem nenhum acesso. Para reativar, entre em supabase.com, abra o projeto e clique em **Restore**. Nenhum dado se perde.
