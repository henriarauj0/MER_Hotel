# 🏨 Sistema de Banco de Dados – Rede de Hotéis

Este projeto contém o **Modelo Entidade-Relacionamento (MER)** de uma Rede de Hotéis.  
O modelo foi desenvolvido a partir de regras de negócio fornecidas e está implementado em **DBML**, pronto para visualização no [dbdiagram.io](https://dbdiagram.io).

---

## 📌 Descrição do Projeto

O objetivo é estruturar um banco de dados que permita controlar:

- Funcionários
- Unidades de hotéis
- Quartos
- Hóspedes
- Reservas
- Pagamentos

O MER foi modelado de acordo com as regras de negócio definidas, sem inclusão de atributos ou entidades extras além do especificado.

---

## 📋 Regras de Negócio

1. **Funcionário**: armazenar CPF, nome, telefone, e-mail, login e senha.  
2. **Hotel**: armazenar id, nome, categoria, telefone, e-mail e endereço (rua, número, complemento, bairro, CEP, cidade, estado).  
3. **Quarto**: armazenar id, número de leitos, tipo (standard, luxo, suíte), preço da diária e status (disponível, ocupado, manutenção).  
4. **Hóspede**: armazenar CPF, nome, telefone, e-mail e endereço completo.  
5. **Reserva**: armazenar id, data de entrada, data de saída e status (ativa, cancelada, concluída).  
6. **Pagamento**: armazenar id, forma (cartão, pix, dinheiro), data, valor total e status (pago, pendente).  
7. **Relacionamentos**:
   - Um hotel possui **um ou vários quartos**.  
   - Um hotel possui **um ou vários funcionários**.  
   - Um funcionário realiza **uma ou várias reservas**.  
   - Um hóspede pode fazer **uma ou várias reservas**.  
   - Uma reserva pode incluir **um ou vários quartos** (relação M:N modelada pela entidade associativa **Reserva_Quarto**).  
   - Uma reserva gera **um pagamento** (relação 1:1).  

---

## 🛠 Estrutura dos Arquivos

- [`rede_hoteis.dbml`](./rede_hoteis.dbml) → Contém a modelagem em DBML (usada no dbdiagram.io).  
- `README.md` → Este arquivo de documentação.  

---

## ▶️ Como Visualizar o MER

1. Abra o site [dbdiagram.io](https://dbdiagram.io).  
2. Crie um novo diagrama.  
3. Copie o conteúdo do arquivo [`rede_hoteis.dbml`](./rede_hoteis.dbml).  
4. Cole no editor do site.  
5. O diagrama será gerado automaticamente mostrando:  
   - Entidades  
   - Atributos  
   - Chaves primárias e estrangeiras  
   - Relacionamentos com cardinalidades.  

---

## 📷 Exemplo de Saída

Ao importar o arquivo `rede_hoteis.dbml` no **dbdiagram.io**, você terá um diagrama como este (simulado):

- Hotel (1) —— (N) Quarto  
- Hotel (1) —— (N) Funcionário  
- Funcionário (1) —— (N) Reserva  
- Hóspede (1) —— (N) Reserva  
- Reserva (N) —— (N) Quarto (via Reserva_Quarto)  
- Reserva (1) —— (1) Pagamento  

---
