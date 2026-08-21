# 📚 BiblioTech CLI — Sistema de Gestão de Biblioteca em Python

![Python Version](https://img.shields.io/badge/Python-3.13.14-blue)
![Architecture](https://img.shields.io/badge/Architecture-POO%20%2B%20Persist%C3%AAncia-green)
![License](https://img.shields.io/badge/License-MIT-yellow)

O **BiblioTech CLI** é uma aplicação orientada a objetos construída em Python para gerenciamento completo de acervos, usuários e empréstimos de livros via linha de comando (CLI). O sistema garante a persistência de dados em formato JSON, simulações de perfis de acesso e aplicação de regras de negócio em tempo real.

---

## 🎯 Destaques de Engenharia e POO

Este projeto foi construído focando na aplicação prática dos princípios da Programação Orientada a Objetos (POO) e modularização de código:

* **Herança e Polimorfismo:** Diferenciação entre `UsuarioComum` e `UsuarioPremium`, aplicando limites dinâmicos de empréstimos simultâneos através de sobrescrita de métodos.
* **Encapsulamento e Métodos de Classe:** Serialização e desserialização de objetos (`to_dict` e `from_dict`) integrados a geradores `@classmethod`.
* **Separação de Responsabilidades (SOC):** 
  * `modelos.py`: Definição das entidades de domínio (`Livro`, `Usuario`, `Emprestimo`).
  * `repositorio.py`: Camada de persistência genérica para arquivos JSON.
  * `biblioteca.py`: Camada de serviço e regras de negócio.
  * `main.py`: Interface CLI e fluxo de navegação.
* **Tratamento de Exceções e Validação:** Garantia de integridade de tipos, datas em padrão ISO e bloqueio de empréstimos duplicados.

---

## 🚀 Funcionalidades

- [x] **Gestão de Acervo:** Cadastro e consulta de disponibilidade de livros.
- [x] **Gestão de Usuários:** Cadastro com categorias dinâmicas (Comum vs. Premium).
- [x] **Controle de Empréstimos:**
  - Validação de disponibilidade do livro.
  - Verificação de limite máximo por tipo de usuário.
  - Bloqueio de empréstimos simultâneos para o mesmo item.
- [x] **Persistência Automática:** Carregamento e salvamento contínuo em arquivos `.json`.
- [x] **Relatórios:** Listagem por status do acervo e histórico ativo.

---

## 🛠️ Tecnologias Utilizadas

* **Linguagem:** Python 3.13.14
* **Manipulação de Dados:** Módulo Nativo `json`
* **Datas/Tempo:** Módulo Nativo `datetime` (padrão ISO 8601)

---

## 📁 Estrutura do Projeto

```text
├── main.py                   # Ponto de entrada (CLI e Menus)
├── biblioteca.py             # Regras de negócio e coordenação do sistema
├── modelos.py                # Classes de domínio (Livro, Usuario, Emprestimo)
├── repositorio.py            # Leitura e escrita de arquivos JSON
├── dados_livros.json         # Base de dados de livros (Gerada automaticamente)
├── dados_usuarios.json       # Base de dados de usuários (Gerada automaticamente)
└── dados_emprestimos.json   # Base de dados de empréstimos (Gerada automaticamente)
```


---

## 🔧 Como Executar o Projeto

1. **Clone o repositório:**
   ```bash
   git clone [https://github.com/andersonfdom/bibliotech-cli.git](https://github.com/andersonfdom/bibliotech-cli.git)
   cd bibliotech-cli
   ```

2. **Execute a aplicação:**
   ```bash
   python main.py
   ```
   *(Não é necessária a instalação de dependências externas, utiliza apenas a biblioteca padrão do Python)*.

---

## 📌 Próximos Passos (Roadmap)

- [ ] Migração da camada de persistência de JSON para **SQLite**.
- [ ] Implementação de datas de devolução previstas com cálculo de multa/atraso.
- [ ] Criação de uma API REST usando **FastAPI**.

---

## 👤 Autor

Desenvolvido por **Anderson Fernando Domingos**  
* LinkedIn: [in/anderson-dom](https://www.linkedin.com/in/anderson-dom/)
* GitHub: [@andersonfdom](https://github.com/andersonfdom)
