# **RF001: Registro** 

- **Descrição:**  
  O sistema deve permitir que novos estabelecimentos se registrem, fornecendo dados básicos e criando uma conta administrativa com acesso ao painel de controle.

---

#### **Processo:**
![alt text](<RF001  Registro.svg>)

---

#### **Pré-condições:**
- O e-mail informado deve ser válido e não registrado previamente.

---

#### **Entradas:**  
| Campo           | Descrição                                                                 | Tipo        | Obrigatório | Validação                            |
|------------------|---------------------------------------------------------------------------|-------------|-------------|---------------------------------------|
| `document`      | Documento único do usuário (CNPJ ou CPF).                                 | String      | Sim         | CPF ou CNPJ válido e único.          |
| `corporateName` | Nome jurídico do estabelecimento (obrigatório se `document` for CNPJ).    | String      | Condicional | -                                     |
| `fullName`      | Nome completo do usuário.                                                 | String      | Sim         | Não pode estar vazio.                |
| `companyName`   | Nome fantasia do estabelecimento.                                         | String      | Sim         | Não pode estar vazio.                |
| `email`         | Endereço de e-mail do usuário.                                            | String      | Sim         | Formato válido e único.              |
| `password`      | Senha para a conta (mínimo 8 caracteres, incluindo maiúsculas e símbolos). | String      | Sim         | Critérios de segurança.              |

---

#### **Saídas:**  
| Tipo          | Descrição                                    |
|---------------|---------------------------------------------|
| E-mail        | Confirmação do registro enviado ao usuário. |
| Mensagem      | Mensagem de sucesso ou erro na interface.   |
| Registro      | Criação da conta administrativa.            |

---

#### **Regras de Negócio:**  
| RN   | Descrição                                                                                     |
|------|-----------------------------------------------------------------------------------------------|
| RN001| **Validação do E-mail:** Deve ser único e no formato válido.                                  |
| RN002| **Segurança da Senha:** Mínimo 8 caracteres, incluindo letras maiúsculas, números e símbolos. |
| RN003| **Nome Completo:** Não pode estar vazio.                                                      |
| RN004| **Documento:** Deve ser único e no formato válido (CPF ou CNPJ).                              |
| RN005| **Razão Social:** Campo obrigatório quando `document` for CNPJ.                               |

