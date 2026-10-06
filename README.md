# Projeto-Multiplataforma-Senai
Projeto desenvolvido para gerenciar monitoramento de erros.

# MetaltechMobile

Sistema de gerenciamento de ocorrências em máquinas industriais, composto por um aplicativo móvel Xamarin.Forms e um sistema web PHP para gerenciamento de dados.

## 📱 Sobre o Projeto

O MetaltechMobile é uma solução completa para registro e acompanhamento de ocorrências e erros em máquinas industriais. O sistema permite que operadores registrem problemas em tempo real e supervisores monitorem e gerenciem essas ocorrências através de dashboards.

### Funcionalidades

#### Aplicativo Móvel (Xamarin.Forms)
- **Autenticação de Usuários**: Login com diferentes perfis (Operador e Supervisor)
- **Registro de Ocorrências**: Operadores podem registrar erros em máquinas com detalhes como:
  - Identificação da máquina
  - Código do erro
  - Descrição detalhada
  - Data e hora automática
  - Nome do operador
- **Gerenciamento de Ocorrências**: Supervisores podem:
  - Consultar todas as ocorrências
  - Atualizar status (Aberto, Em Análise, Resolvido, Fechado)
  - Excluir ocorrências
- **Dashboard Estatístico**: Visualização de métricas como:
  - Total de ocorrências
  - Máquina com mais ocorrências
  - Média de ocorrências por dia
  - Estatísticas por máquina

#### Sistema Web (PHP)
- **Autenticação de Usuários**: Login com diferentes perfis (Operador e Supervisor)
- **Registro de Ocorrências**: Operadores podem registrar erros em máquinas com detalhes como:
  - Identificação da máquina
  - Código do erro
  - Descrição detalhada
  - Data e hora automática
  - Nome do operador
- **Gerenciamento de Ocorrências**: Supervisores podem:
  - Consultar todas as ocorrências
  - Atualizar status (Aberto, Em Análise, Resolvido, Fechado)
  - Excluir ocorrências
- **Dashboard Estatístico**: Visualização de métricas como:
  - Total de ocorrências no mês
  - Máquina com mais ocorrências
  - Média de ocorrências por dia
  - Estatísticas por máquina
- **API RESTful**: Endpoints para comunicação:
  - `listar_ocorrencias.php` - Lista todas as ocorrências
  - `registrar_ocorrencia.php` - Registra nova ocorrência
  - `atualizar_status.php` - Atualiza status de ocorrência
  - `excluir_ocorrencia.php` - Exclui ocorrência

## 🛠️ Tecnologias Utilizadas

### Aplicativo Móvel
- **Framework**: Xamarin.Forms 5.0.0.2196
- **Linguagem**: C# (.NET Standard 2.0)
- **Plataforma**: Android
- **Bibliotecas**:
  - `MySqlConnector` 2.6.2 - Conexão com banco de dados
  - `Newtonsoft.Json` 13.0.4 - Serialização JSON
  - `Xamarin.Essentials` 1.7.0 - Funcionalidades essenciais do dispositivo

### Sistema Web
- **Backend**: PHP
- **Frontend**: HTML5, CSS3, JavaScript
- **Banco de Dados**: MySQL
- **Comunicação**: HTTP/JSON

## 📁 Estrutura do Projeto

```
MetaltechMobile/
├── MetaltechMobile/
│   ├── MetaltechMobile/          # Projeto principal Xamarin.Forms
│   │   ├── MetaltechMobile/
│   │   │   ├── Models/           # Modelos de dados
│   │   │   │   ├── Ocorrencia.cs
│   │   │   │   └── RespostaOcorrencias.cs
│   │   │   ├── LoginPage.xaml/cs     # Tela de login
│   │   │   ├── MenuPage.xaml/cs      # Menu principal
│   │   │   ├── OcorrenciaPage.xaml/cs # Registro de ocorrências
│   │   │   ├── OcorrenciasPage.xaml/cs # Lista de ocorrências
│   │   │   ├── DashboardPage.xaml/cs  # Dashboard estatístico
│   │   │   └── App.xaml/cs           # Ponto de entrada
│   │   └── MetaltechMobile.Android/   # Projeto Android específico
│   └── MetaltechMobile.sln            # Solução Visual Studio
└── README.md
```

### Sistema Web PHP
```
htdocs/Metaltech/Metaltech/
├── index.php                   # Página de login
├── login.php                   # Processamento de login
├── logout.php                  # Logout
├── menu.php                    # Menu principal
├── registrar.php               # Formulário de registro
├── registrar_ocorrencia.php    # API: Registrar ocorrência
├── ocorrencias.php             # Lista de ocorrências
├── listar_ocorrencias.php      # API: Listar ocorrências
├── atualizar_status.php        # API: Atualizar status
├── excluir_ocorrencia.php      # API: Excluir ocorrência
├── dashboard.php               # Dashboard estatístico
├── conecta.php                 # Conexão com banco de dados
├── script.js                   # JavaScript do sistema
├── style.css                   # Estilos CSS
└── teste.php                   # Arquivo de teste
```

## 🚀 Configuração e Instalação

### Pré-requisitos

- Visual Studio 2019 ou superior (com workload de desenvolvimento mobile com .NET)
- Android SDK
- Emulador Android ou dispositivo físico
- Servidor web com suporte a PHP (XAMPP, WAMP, ou similar)
- MySQL Server

### Configuração do Banco de Dados

1. Crie um banco de dados MySQL
2. Crie a tabela de ocorrências com a seguinte estrutura:



### Configuração do Sistema Web

1. Configure o servidor web (XAMPP/WAMP)
2. Coloque os arquivos PHP em: `htdocs/Metaltech/Metaltech/`
3. Configure a conexão com o banco de dados em `conecta.php`:
   - Host: `sql.freedb.tech`
   - Porta: `3306`
   - Banco: `freedb_ZbTuse3Y`
   - Usuário: `u_huyrgA`
   - Senha: `3zQdQ3OXWTk9`
4. Ajuste a URL base no código do aplicativo conforme necessário

### Executando o Sistema Web

1. Inicie o servidor Apache e MySQL do XAMPP
2. Acesse: `http://localhost/Metaltech/Metaltech/`
3. Faça login com as credenciais disponíveis

### Executando o Aplicativo Móvel

1. Abra o arquivo `MetaltechMobile.sln` no Visual Studio
2. Selecione o projeto `MetaltechMobile.Android` como projeto de inicialização
3. Configure o emulador ou dispositivo Android
4. Pressione F5 ou clique em "Iniciar" para compilar e executar

## 👤 Credenciais de Acesso

O sistema possui dois perfis de usuário pré-configurados:

|| Perfil      | Usuário    | Senha  |
||-------------|------------|--------|
|| Operador    | operador   | 1234    |
|| Supervisor  | supervisor | admin   |

**Nota**: Para produção, implemente um sistema de autenticação seguro com hashing de senhas e armazenamento em banco de dados.

## 📋 Uso

### Como Operador (Sistema Web ou App Móvel)
1. Faça login com as credenciais de operador
2. Selecione "Registrar Ocorrência"
3. Preencha os dados da máquina, código do erro e descrição
4. Confirme o registro
5. Opcionalmente, registre outra ocorrência ou retorne ao menu

### Como Supervisor (Sistema Web ou App Móvel)
1. Faça login com as credenciais de supervisor
2. Acesse o menu com todas as opções disponíveis
3. **Consultar Ocorrências**: Visualize e gerencie ocorrências existentes
4. **Dashboard**: Analise estatísticas e métricas
5. **Registrar Ocorrências**: Registe novos problemas (se necessário)

## 🔧 Personalização

### Alterar URL da API (App Móvel)

Para alterar o endereço do servidor web, modifique as URLs nos seguintes arquivos:
- `DashboardPage.xaml.cs` (linha 32)
- `OcorrenciasPage.xaml.cs` (linha 35-36)
- `OcorrenciaPage.xaml.cs` (linha 81-82)
- `OcorrenciasPage.xaml.cs` (linha 119)
- `OcorrenciasPage.xaml.cs` (linha 157)

Substitua `http://10.0.2.2/Metaltech/Metaltech/` pelo endereço do seu servidor.

### Alterar Conexão com Banco de Dados (Sistema Web)

Edite o arquivo `conecta.php` para alterar as credenciais do banco de dados.

### Adicionar Novos Perfis

Para adicionar novos perfis de usuário, edite:
- **App Móvel**: Método `btnEntrar_Clicked` em `LoginPage.xaml.cs`
- **Sistema Web**: Função de login em `script.js`

## 📄 Modelo de Dados

### Ocorrencia
```csharp
public class Ocorrencia
{
    public int Id { get; set; }
    public string Maquina { get; set; }
    public string CodigoErro { get; set; }
    public string DescricaoErro { get; set; }
    public DateTime DataHora { get; set; }
    public string Operador { get; set; }
    public string Status { get; set; }
}
```

### RespostaOcorrencias
```csharp
public class RespostaOcorrencias
{
    public bool sucesso { get; set; }
    public List<Ocorrencia> dados { get; set; }
}
```

## 🐛 Troubleshooting

### Problemas de Conexão (App Móvel)
- Verifique se o servidor web está rodando
- Confirme se o emulador Android pode acessar `10.0.2.2` (localhost do host)
- Verifique as permissões de internet no `AndroidManifest.xml`

### Problemas de Conexão (Sistema Web)
- Verifique se o servidor Apache e MySQL estão rodando
- Confirme as credenciais em `conecta.php`
- Verifique se o banco de dados e tabela existem

### Erros de Compilação (App Móvel)
- Certifique-se de que todos os pacotes NuGet foram restaurados
- Verifique se a versão do .NET SDK está instalada corretamente
- Limpe e recompile a solução

### Dados Não Aparecendo
- Verifique a conexão com o banco de dados MySQL
- Confirme se a tabela de ocorrências existe e contém dados
- Verifique os logs de erro do PHP

## 📝 Licença

Este projeto é desenvolvido para fins educacionais e uso interno da Metaltech.

## 👥 Contribuição

Contribuições são bem-vindas! Para adicionar novas funcionalidades:

1. Fork o projeto
2. Crie uma branch para sua feature (`git checkout -b feature/NovaFuncionalidade`)
3. Commit suas mudanças (`git commit -m 'Adiciona nova funcionalidade'`)
4. Push para a branch (`git push origin feature/NovaFuncionalidade`)
5. Abra um Pull Request



**Desenvolvido com ❤️ usando Xamarin.Forms e PHP**
