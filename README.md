# APM 4.0 — Coutinho (versão corrigida)

## Publicar no GitHub Pages
1. Abra o repositório `Simulador-APM` e acesse a aba **Code**.
2. Remova ou substitua o `index.html` anterior **na raiz da branch main** pelo `index.html` deste pacote. O nome precisa ser exatamente `index.html` (letras minúsculas).
3. Faça **Commit changes**. Em **Settings > Pages**, selecione `Deploy from a branch`, branch `main`, pasta `/(root)`.
4. Aguarde a publicação e abra `https://lucasacoutinho-sketch.github.io/Simulador-APM/` com `Ctrl+Shift+R`.
5. O painel deve abrir em modo demonstração, sem conexão com API. Teste os três cenários no seletor **Teste de condição**.

**Importante:** não envie apenas o arquivo ZIP para o GitHub. Extraia-o e envie `index.html` diretamente para a raiz do repositório. Arquivos antigos `app.js`, `style.css` e `config.js` podem permanecer, mas não são utilizados por esta versão.

## Integração com Google Apps Script
- Cole `Code.gs` em um projeto Apps Script vinculado à planilha de dados.
- Implante como **Aplicativo da Web** executado por sua conta, com permissões adequadas ao caso de uso.
- No `index.html`, localize `const CONFIG={API_URL:'',DEMO:true};` e coloque a URL da implantação terminada em `/exec`, alterando `DEMO:false`.
- A leitura por GET depende de acesso autorizado e da política de CORS do navegador. Se houver bloqueio, é necessário um intermediário/backend apropriado. Não publique dados industriais sensíveis em uma implantação pública.
- O POST deve ser enviado por um cliente de aquisição autorizado. O site não envia POST nem controla a máquina.

## Diagnóstico
- Alerta: temperatura >= 65 °C, vibração >= 4,5 mm/s ou corrente >= 35 A.
- Crítico: temperatura >= 80 °C, vibração >= 7,1 mm/s ou corrente >= 45 A.
- Limites apenas ilustrativos; valide-os com documentação do ativo e profissional responsável.
- A condição NOVO/ANTIGO não comprova falha do sensor. Recomenda-se inspeção e confirmação da leitura.
