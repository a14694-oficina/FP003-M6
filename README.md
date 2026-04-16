# Sistema de Gestão de Infraestrutura de Rede Escolar

## Descrição do Projeto

Este projeto consiste num sistema web para a gestão de infraestruturas de rede em ambientes escolares. Permite o registo e controlo de salas, equipamentos, técnicos e intervenções realizadas nos dispositivos de rede. O sistema foi desenvolvido para facilitar a organização e manutenção dos recursos de rede, garantindo um acompanhamento eficaz das operações.

## Funcionalidades

*   **Gestão de Salas**: Registo e visualização dos espaços físicos onde os equipamentos estão instalados.
*   **Gestão de Equipamentos**: Registo detalhado de dispositivos de rede (tipo, marca, modelo, IP) e a sua associação a salas específicas.
*   **Gestão de Técnicos**: Registo de profissionais responsáveis pelas intervenções, incluindo nome, email e contacto.
*   **Gestão de Intervenções**: Registo das intervenções realizadas nos equipamentos, associando-as a um equipamento e a um técnico responsável.
*   **Listagem de Equipamentos com Salas**: Visualização dos equipamentos com o nome da sala correspondente.
*   **Consulta de Intervenções Detalhadas**: Visualização das intervenções com informações compreensíveis sobre o equipamento e o técnico.
*   **Identificação de Equipamentos sem Intervenções**: Funcionalidade para listar equipamentos que ainda não tiveram intervenções registadas.
*   **Autenticação de Utilizadores**: Sistema de login para acesso seguro à aplicação.

## Tecnologias Utilizadas

*   **Backend**: PHP
*   **Frontend**: HTML, CSS
*   **Base de Dados**: MySQL

## Estrutura da Base de Dados

A base de dados é composta por quatro tabelas principais, que se relacionam para gerir a infraestrutura de rede:

| Tabela         | Descrição                                                                 | Chaves Estrangeiras |
| :------------- | :------------------------------------------------------------------------ | :------------------ |
| `salas`        | Armazena informações sobre os espaços físicos.                            | -                   |
| `equipamentos` | Guarda detalhes dos dispositivos de rede e a sua localização em salas.    | `id_sala`           |
| `tecnicos`     | Contém os dados dos profissionais que realizam as intervenções.           | -                   |
| `intervencoes` | Regista as ações de manutenção, ligando equipamentos e técnicos.          | `id_equipamento`, `id_tecnico` |

### Relações

*   Uma `sala` pode ter múltiplos `equipamentos`.
*   Um `equipamento` pode ter múltiplas `intervencoes`.
*   Um `tecnico` pode realizar múltiplas `intervencoes`.

## Instalação

Para configurar o projeto localmente, siga os passos abaixo:

1.  **Clone o repositório:**

    ```bash
    git clone https://github.com/seu-usuario/m6-infraestrutura.git
    cd m6-infraestrutura
    ```

2.  **Configurar a Base de Dados:**

    *   Crie uma base de dados MySQL com o nome `if0_40156182_db_infraestrutura` (ou ajuste o nome no ficheiro `bd.sql`).
    *   Importe o ficheiro `bd.sql` para a sua base de dados:

        ```bash
        mysql -u seu_usuario -p if0_40156182_db_infraestrutura < bd.sql
        ```

3.  **Configurar a Conexão PHP:**

    *   Edite o ficheiro `config/ligacao.php` com as suas credenciais de base de dados (servidor, utilizador, palavra-passe).

4.  **Servidor Web:**

    *   Coloque os ficheiros do projeto num servidor web (por exemplo, Apache ou Nginx) com suporte a PHP.

## Utilização

Após a instalação, aceda ao projeto através do seu navegador web. Será redirecionado para a página de login (`login.php`). Após a autenticação, poderá navegar pelas diferentes secções do sistema para gerir salas, equipamentos, técnicos e intervenções.
