# Neurox · Painel de OPME

Painel de pedidos, autorizações e cirurgias de OPME, com ranking por vendedor e por médico, prazos em dias úteis, histórico de preços por convênio e relatórios em PDF.

- **Site:** um único arquivo `index.html`, publicado no GitHub Pages (gratuito)
- **Banco de dados:** Supabase, projeto `neurox-painel-opme` (plano gratuito, região São Paulo)

## Como publicar no GitHub Pages

1. Entre no GitHub e clique em **New repository**. Nome sugerido: `neurox-painel`. Pode deixar como **Public**, porque os dados ficam no Supabase, protegidos por login, e não no código.
2. Na página do repositório, clique em **Add file > Upload files**, envie o `index.html` e este `README.md`, e clique em **Commit changes**.
3. Vá em **Settings > Pages**. Em *Source*, escolha **Deploy from a branch**, depois a branch **main** e a pasta **/ (root)**, e clique em **Save**.
4. Em um ou dois minutos, o endereço aparece no topo da mesma página. Ele tem o formato `https://SEU-USUARIO.github.io/neurox-painel/`.

## Primeiro acesso (faça isso antes de qualquer outra pessoa)

1. Abra o endereço do site e clique em **Criar conta** com o seu e-mail.
   **A primeira conta criada vira automaticamente a dona do painel.** Qualquer outra conta só enxerga os dados depois que você liberar o e-mail em **Cadastros > Acessos**.
2. Confirme pelo link que chega no seu e-mail e depois entre com e-mail e senha.
3. Ajuste recomendado no Supabase: abra o projeto **neurox-painel-opme** e vá em **Authentication > URL Configuration**. Em **Site URL**, coloque o endereço do GitHub Pages. Assim, os links de confirmação e de recuperação de senha voltam direto para o painel.

## No celular

Abra o endereço no navegador e use **Adicionar à tela de início** (no Safari, pelo botão Compartilhar; no Chrome, pelo menu ⋮). O painel abre como um aplicativo.

## Como usar

1. **Cadastros:** cadastre vendedores, médicos, convênios e hospitais. Os feriados nacionais, de Sergipe e de Aracaju de 2026 e 2027 já vêm cadastrados.
2. **Novo processo:** informe o paciente, o vendedor, o médico, o convênio, o hospital e a data da solicitação. Em seguida, lance os itens com quantidade e valor unitário cotado.
3. **Mover etapa:** use o fluxo Pedido → Cotação → Em análise (aguardando autorização) → Autorizada → Agendada → Realizada, ou marque como Negada ou Cancelada. Dá para informar a data e a hora reais da mudança.
4. **Valores autorizados:** quando o processo for autorizado, preencha o valor unitário autorizado de cada item. Esses valores formam o histórico de preços por convênio, e o painel sugere o último valor aprovado na próxima cotação.
5. **Relatórios:** gere um PDF por vendedor ou um PDF consolidado para a diretoria. Há a opção de mostrar só as iniciais dos pacientes (LGPD). Também é possível exportar tudo em CSV para o Excel.

## Prazos

- O prazo de referência é de **21 dias úteis** contados da data da solicitação, sem contar fins de semana nem feriados cadastrados.
- **Verde:** no prazo. **Amarelo:** a partir de 15 dias úteis. **Vermelho:** acima de 21 dias úteis.
- Cada processo mostra o **tempo na etapa atual** e o **tempo total desde o pedido**.
- Para mudar esses números, edite `PRAZO_DU` e `ALERTA_DU` no bloco `CONFIGURAÇÃO`, no início do script do `index.html`.

## Identidade visual

As cores ficam no início do `<style>`, nas variáveis `--brand` (principal) e `--brand2` (secundária). Quando a paleta oficial e o logo da Neurox estiverem prontos, basta trocar esses valores e o SVG do logo, na função `logoSvg`.

## Plano gratuito do Supabase

No plano gratuito, o projeto é **pausado depois de 7 dias sem nenhum acesso**. Os dados não são perdidos: para reativar, entre em supabase.com, abra o projeto e clique em **Restore**. Usando o painel com frequência, isso não acontece.
