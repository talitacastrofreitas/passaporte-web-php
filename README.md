# 🛂 Passaporte Bahiana Covid-19 (Portal do Usuário)
O **Passaporte Bahiana Covid-19** é um portal web conceitual de autodeclaração de saúde desenvolvido para a **Escola Bahiana de Medicina e Saúde Pública (EBMSP)**. O sistema permite que alunos, professores, funcionários e colaboradores externos declarem seu estado de saúde relacionado a sintomas da Covid-19 antes de acessarem as instalações do campus.
Este projeto é a interface voltada ao usuário final, complementando o painel de gerenciamento **Passaporte-ADM**.

---
## 🚀 Fluxo de Navegação
1. **Identificação & Perfil (`index.php`):**
   - O usuário escolhe seu perfil institucional (Aluno, Professor, Terceirizado, Visitante, etc.).
   - Digita seu CPF (com formatação automática via máscara JavaScript).
   - Deve ler e concordar com os Termos e Políticas de Privacidade para liberar o botão de acesso ao formulário.
2. **Formulário de Sintomas (`formulario.php`):**
   - Apresenta um questionário com uma lista de possíveis sintomas relacionados à Covid-19 (febre, tosse, perda de olfato/paladar, dor de garganta, etc.) ou teste positivo recente.
   - **Lógica Dinâmica (`script.js`):** Se qualquer sintoma for selecionado, a opção *"Não apresentei nenhum dos sintomas acima"* é desmarcada e bloqueada, e um campo de preenchimento obrigatório para telefone celular é exibido para posterior contato médico.
3. **Página de Resultados:**
   - **Apto (`validacao.php`):** Se nenhum sintoma for reportado, o sistema gera uma liberação verde com um ícone de verificação (`img/verificado.png`) e prazo de validade.
   - **Não Apto (`n-validacao.php`):** Caso reporte algum sintoma, o usuário é instruído a aguardar o contato da Medicina Ocupacional da instituição, apresentando um selo de restrição vermelho (`img/n-verificado.png`).
---
## 📂 Estrutura do Projeto
```bash
Passaporte/
├── css/
│   ├── form.css           # Estilos específicos do questionário de sintomas
│   ├── n-valido.css       # Estilo da página de resultado de não autorização
│   ├── style.css          # Estilo da tela de login/perfil principal
│   └── valido.css         # Estilo da página de resultado de liberação verde
├── img/
│   ├── background.jpg     # Imagem de fundo do portal
│   ├── logo.png           # Logotipo institucional da Escola Bahiana
│   ├── n-verificado.png   # Selo vermelho de restrição de acesso
│   └── verificado.png     # Selo verde de liberação de acesso
├── index.php              # Tela inicial de perfil e CPF
├── formulario.php         # Questionário com checklist de sintomas
├── validacao.php          # Tela de passaporte válido (liberação de entrada)
├── n-validacao.php        # Tela de passaporte inválido (bloqueio temporário)
├── script.js              # Lógica de validação cruzada do checklist de sintomas
└── README.md              # Documentação do projeto
```
---
## 🛠️ Tecnologias Utilizadas
- **PHP:** Estruturação básica de páginas dinâmicas.
- **Bootstrap 5 & 4:** Utilizado para os estilos de grade responsiva, caixas de diálogo, botões de ação e listas.
- **JavaScript (Vanilla):** Lógica local para habilitar/desabilitar botões de termos e estruturar o array de respostas.
- **jQuery & jQuery Mask Plugin:** Biblioteca Javascript usada para aplicar máscaras de entrada em tempo real nos campos de CPF (`000.000.000-00`) e Celular (`(00) 00000-0000`).
---
## 💻 Como Rodar o Projeto
Como as regras de navegação do formulário e validação do passaporte estão implementadas no front-end, o projeto pode ser executado localmente de forma estática.
1. Baixe ou clone os arquivos do repositório em sua máquina local.
2. Como o projeto possui arquivos `.php`, você pode executá-lo em um servidor local como o [XAMPP](https://www.apachefriends.org/) ou rodar o servidor embutido do PHP na pasta do projeto:
   ```bash
   php -S localhost:8000
   ```
3. Abra o navegador no endereço: [http://localhost:8000](http://localhost:8000)
4. Certifique-se de possuir acesso à internet para carregar as dependências de estilo (Bootstrap) e máscaras JavaScript importadas via CDN.
