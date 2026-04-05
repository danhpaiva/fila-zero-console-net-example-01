# FilaZero - Sistema de Login (Console)

Este é um módulo de autenticação desenvolvido em **C#** para o ecossistema **.NET Core**. O sistema simula uma interface de terminal (CLI) moderna e intuitiva para o projeto **FilaZero**, focando em usabilidade e segurança básica na entrada de dados.

## 🚀 Funcionalidades

* **Interface Estilizada:** Utiliza caracteres ASCII e cores no terminal para uma melhor experiência do usuário.
* **Mascaramento de Senha:** Implementação de lógica para capturar a senha sem exibi-la em texto plano, utilizando asteriscos (`*`).
* **Feedback Visual:** Inclui uma simulação de *loading* para processos de autenticação.
* **Suporte a UTF-8:** Configurado para exibir corretamente caracteres especiais e emojis no console.

## 🛠️ Tecnologias Utilizadas

* **Linguagem:** C#
* **Plataforma:** .NET 6.0 ou superior
* **Namespace Principal:** `System.Text`, `System.Threading`

## 📋 Estrutura do Código

O projeto segue uma abordagem procedural organizada por métodos estáticos para facilitar a leitura:

* `DesenharTela()`: Renderiza o cabeçalho estilizado do sistema.
* `ExecutarLogin()`: Orquestra o fluxo de entrada de credenciais.
* `LerSenha()`: Método especializado em capturar inputs de teclado e mascarar a exibição.
* `ValidarLogin()`: Contém a regra de negócio para verificação de credenciais (Mock).

## 💻 Como Executar

1.  Certifique-se de ter o **SDK do .NET** instalado.
2.  Clone o repositório:
    ```bash
    git clone https://github.com/seu-usuario/nome-do-repositorio.git
    ```
3.  Navegue até a pasta do projeto e execute:
    ```bash
    dotnet run
    ```

### Credenciais de Teste (Mock)
* **Email:** `admin@filazero.com`
* **Senha:** `123456`

## 📂 Trechos Relevantes

O sistema utiliza o `StringBuilder` para manipulação eficiente da senha e o método `Console.ReadKey(true)` para interceptar as teclas sem ecoar o caractere original no terminal.

```csharp
// Exemplo de lógica de mascaramento
tecla = Console.ReadKey(true);
if (!char.IsControl(tecla.KeyChar))
{
    senha.Append(tecla.KeyChar);
    Console.Write("*");
}
```

---

## 🧠 Interface e Usabilidade (Heurísticas de Nielsen)

Este projeto foi desenvolvido aplicando princípios fundamentais de usabilidade para garantir que, mesmo em um ambiente de terminal, a experiência do usuário seja fluida e clara.

### 1. Visibilidade do Status do Sistema
O sistema mantém o usuário informado sobre o que está acontecendo em tempo real.
* **Aplicação:** O método `MostrarLoading()` fornece feedback visual enquanto o sistema "processa" a autenticação, evitando a incerteza se o programa travou ou está operando.

### 2. Correspondência entre o Sistema e o Mundo Real
Utilizamos uma linguagem e convenções familiares ao usuário.
* **Aplicação:** O uso de ícones (emojis) como 📧 para e-mail e 🔒 para senha, além do título da janela (`Console.Title`), ajuda o usuário a identificar rapidamente o contexto de cada campo.

### 3. Consistência e Padrões
O projeto segue o padrão esperado de sistemas de segurança modernos.
* **Aplicação:** O mascaramento da senha com asteriscos (`*`) é um padrão universal de IHC (Interação Humano-Computador) para proteger informações sensíveis, garantindo que o usuário entenda que sua privacidade está sendo preservada.

### 4. Prevenção de Erros e Suporte a Erros
O sistema foi desenhado para evitar entradas inválidas e tratar ações do usuário.
* **Aplicação:** O tratamento da tecla `Backspace` no método `LerSenha()` permite que o usuário corrija erros de digitação em tempo real, mantendo o controle sobre a interação sem precisar reiniciar o processo.

### 5. Estética e Design Minimalista
O design foca no que é essencial para a tarefa de login.
* **Aplicação:** A moldura em ASCII organiza as informações visualmente, destacando o título do sistema (**FILAZERO**) e o propósito da tela, sem poluição visual desnecessária.

---
