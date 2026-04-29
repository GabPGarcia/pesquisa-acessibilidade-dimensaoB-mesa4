## Sobre esta pesquisa
Análise sobre como a acessibilidade digital é tratada por empresas, legislações e casos reais, investigando se ela é aplicada como obrigação técnica ou apenas como diferencial.

## O que descobrimos (Principais Achados)
- A acessibilidade digital é uma obrigação legal no Brasil, garantida pela Lei Brasileira de Inclusão (Lei nº 13.146/2015), exigindo que sistemas sejam utilizáveis por todos. (Fonte: LBI, 2015)
- O aumento de processos baseados na ADA nos EUA mostra que a falta de acessibilidade está gerando risco jurídico e financeiro crescente para empresas. (Fonte: ADA Lawsuits Report, 2023)
- Casos como o da Domino’s Pizza comprovam que sites e aplicativos também são considerados espaços públicos, portanto devem ser acessíveis. (Fonte: Robles v. Domino’s Pizza, LLC)
- Empresas brasileiras como PicPay e Banco Original ainda apresentam lacunas estruturais em acessibilidade, tratando o tema como secundário em relação a segurança ou UX tradicional. (Fonte: análise de UX e documentação institucional)
- Big Techs como Microsoft, Apple e Google tratam acessibilidade como requisito nativo de engenharia, incorporado desde o início do desenvolvimento. (Fonte: práticas corporativas de acessibilidade)

## Ferramentas / Casos / Legislação
| Categoria              | Exemplo                           | Situação                        | Impacto                 |
| ---------------------- | --------------------------------- | ------------------------------- | ----------------------- |
| **Legislação Brasil**  | Lei Brasileira de Inclusão (2015) | Obriga acessibilidade digital   | Responsabilização legal |
| **Legislação EUA**     | ADA (1990)                        | Aplicada ao digital via न्याय   | Aumento de processos    |
| **Caso Internacional** | Domino’s Pizza                    | Falha em leitor de tela         | Precedente jurídico     |
| **Caso Brasil**        | BRB Banco                         | Falha em acessibilidade         | Indenização             |
| **Empresa Nacional**   | PicPay                            | Libras, mas sem política formal | Parcial                 |
| **Empresa Nacional**   | Banco Original                    | Problemas de contraste e UX     | Deficiente              |
| **Big Techs**          | Google, Apple, Microsoft          | Acessibilidade integrada        | Referência global       |


## Como isso afeta o nosso trabalho com desenvolvedores
- Acessibilidade vira requisito obrigatório, não opcional (impacta desde o início do projeto)
- Código precisa ser semântico e navegável por teclado (usar `button`, `label`, evitar `div` interativa)
- Interfaces devem ser perceptíveis (contraste adequado + textos alternativos em imagens)
- Pensar em acessibilidade desde o desenvolvimento, não como correção no final

### Exemplo de código acessível

```html
<!DOCTYPE html>
<html lang="pt-BR"> <!-- Define idioma para leitores de tela -->
<head>
  <meta charset="UTF-8"> <!-- Suporte a acentuação -->
  <title>Exemplo Acessível</title>

  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #ffffff; /* Fundo claro */
      color: #111111; /* Alto contraste (acessibilidade visual) */
    }

    button:focus {
      outline: 3px solid #005fcc; /* Destaque visível ao navegar com teclado */
    }
  </style>
</head>

<body>

  <main> <!-- Estrutura semântica -->
    <h1>Cadastro</h1>

    <!-- Label associado ao input (melhora leitura por screen readers) -->
    <label for="nome">Nome:</label>
    <input id="nome" type="text" />

    <br><br>

    <!-- Botão semântico (evita usar div clicável) -->
    <button onclick="enviarFormulario()" aria-label="Enviar formulário">
      Enviar
    </button>

    <!-- Região dinâmica acessível (leitores anunciam mudanças) -->
    <p id="status" aria-live="polite"></p>
  </main>

  <script>
    function enviarFormulario() {
      const nome = document.getElementById("nome").value;
      const status = document.getElementById("status");

      if (nome.trim() === "") {
        status.textContent = "Por favor, preencha o nome."; // Feedback acessível
      } else {
        status.textContent = "Formulário enviado com sucesso!"; // Feedback acessível
      }
    }
  </script>

</body>
</html>
```

## Referências
- Brasil. Lei Brasileira de Inclusão da Pessoa com Deficiência (Lei nº 13.146). 2015.
https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2015/lei/l13146.htm
- Associação Brasileira de Normas Técnicas (ABNT). ABNT NBR 17225: Acessibilidade digital para web. 2022.
https://www2.camara.leg.br/a-camara/estruturaadm/gestao-na-camara-dos-deputados/responsabilidade-social-e-ambiental/acessibilidade/pdfs/ABNTNBR17225AcessibilidadeDigitalparaWeb.pdf
- Ministério Público Federal (MPF). Falta de acessibilidade nos sites é tema de ação do Ministério Público Federal. 2023. https://mwpt.com.br/falta-de-acessibilidade-nos-sites-e-tema-de-acao-do-ministerio-publico-federal/
- U.S. Court of Appeals for the Ninth Circuit. Robles v. Domino's Pizza, LLC. 2019.
https://law.justia.com/cases/federal/appellate-courts/ca9/17-55504/17-55504-2019-01-15.html
- Microsoft. Accessibility at Microsoft. 2024.
https://www.microsoft.com/en-us/accessibility
- Governo Federal do Brasil. Acessibilidade Digital. 2023.
https://www.gov.br/governodigital/pt-br/acessibilidade-e-usuario/acessibilidade-digital
