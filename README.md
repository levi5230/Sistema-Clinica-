# 🏥 Sistema de Gestão de Clínica Médica

![Java](https://img.shields.io/badge/Java-21-orange?style=flat-square&logo=java)
![MySQL](https://img.shields.io/badge/MySQL-8.x-blue?style=flat-square&logo=mysql)
![Swing](https://img.shields.io/badge/GUI-Java%20Swing-green?style=flat-square)
![Status](https://img.shields.io/badge/Status-Concluído-brightgreen?style=flat-square)

> Trabalho Prático — 2ª Prova | Linguagens de Programação VI  
> Universidade Kimpa Vita — Instituto Politécnico  
> Docente: **Moyo Kanivengidio** | 2º Ano de Engenharia Informática

-----

## 📋 Descrição

Sistema desktop desenvolvido em Java para automatizar e optimizar a gestão de uma clínica médica. A solução integra módulos de gestão de pacientes, médicos, consultas, prontuários electrónicos e relatórios gerenciais, com controlo de acesso baseado em perfis de utilizador.

-----

## ✅ Funcionalidades

|Módulo           |Descrição                                                  |
|-----------------|-----------------------------------------------------------|
|🔐 **Login**      |Autenticação com 3 perfis: Admin, Médico, Recepcionista    |
|👤 **Pacientes**  |Cadastro, edição, inactivação e pesquisa por nome/CPF      |
|🩺 **Médicos**    |Cadastro com CRM, especialidade e contactos                |
|📅 **Consultas**  |Agendamento com verificação de conflito de horários        |
|📋 **Prontuários**|Diagnóstico, prescrição e histórico clínico                |
|📊 **Relatórios** |Consultas por médico, pacientes activos e resumo por status|

-----

## 🛠️ Tecnologias Utilizadas

- **Java JDK 21** — Linguagem de programação principal
- **Java Swing** — Interface gráfica desktop
- **MySQL 8.x** — Banco de dados relacional
- **JDBC** — Conectividade Java ↔ MySQL
- **MySQL Connector/J 9.7.0** — Driver JDBC
- **IntelliJ IDEA** — IDE de desenvolvimento
- **Padrões:** MVC + DAO + Singleton

-----

## 🏗️ Arquitectura

```
src/
└── com/clinica/
    ├── model/          # Entidades: Usuario, Paciente, Medico, Consulta, Prontuario
    ├── dao/            # Acesso a dados: PacienteDAO, MedicoDAO, ConsultaDAO...
    ├── controller/     # Lógica: PacienteController, ConsultaController...
    ├── view/forms/     # Telas Swing: TelaLogin, TelaPrincipal, TelaPacientes...
    ├── connection/     # ConexaoDB (padrão Singleton)
    └── util/           # SenhaUtil (hash SHA-256)
```

-----

## 🗄️ Base de Dados

O banco de dados possui **8 tabelas** com todos os relacionamentos:

```
usuarios ──── medicos ──── especialidades
    │               │
    └── pacientes   └── consultas ──── prontuarios
                                           │
                               prontuario_medicamentos ──── medicamentos
```

### Configurar o MySQL

1. Abre o **MySQL Workbench**
1. Vai a **File → Open SQL Script**
1. Selecciona o ficheiro `clinica_medica_completo.sql`
1. Executa com o botão **⚡**

-----

## ▶️ Como Executar

### Pré-requisitos

- Java JDK 21 ou superior
- MySQL Server 8.x instalado e em execução
- IntelliJ IDEA

### Passos

1. **Clona o repositório:**

```bash
git clone https://github.com/levi5230/sistema-clinica-medica.git
```

1. **Configura o banco de dados:**
- Executa o script `clinica_medica_completo.sql` no MySQL Workbench
1. **Abre no IntelliJ:**
- `File → Open` → selecciona a pasta `clinica`
- Clica direito em `src` → `Mark Directory as → Sources Root`
1. **Adiciona o driver MySQL:**
- `File → Project Structure → Libraries → +` → selecciona `lib/mysql-connector-j-9.7.0.jar`
1. **Executa:**
- Abre `Main.java` → clica direito → `Run 'Main.main()'`

-----

## 🔑 Credenciais de Teste

|Utilizador         |Login       |Senha   |Perfil       |
|-------------------|------------|--------|-------------|
|Administrador Geral|`admin`     |`123456`|ADMIN        |
|Dr. Carlos Mendes  |`carlos.med`|`123456`|MÉDICO       |
|Ana Recepcionista  |`ana.recep` |`123456`|RECEPCIONISTA|

-----

## 🔒 Segurança

- Senhas armazenadas com **hash SHA-256** — nunca em texto puro
- **PreparedStatement** em todas as queries — prevenção de SQL Injection
- Restrição de acesso por perfil de utilizador
- `UNIQUE(medico_id, data_hora)` no banco — prevenção de conflitos de horário

-----

## 👥 Autores

|Nome|Função       |
|----|-------------|
|Levi|Desenvolvedor|


> 📍 Universidade Kimpa Vita — Uíge, Angola  
> 📅 Junho de 2026

-----

## 📄 Licença

Projecto académico desenvolvido para fins educacionais.  
© 2026 — Universidade Kimpa Vita