# ✅ Validador de CPF em Python

Projeto em Python que valida se um número de CPF é autêntico, utilizando o algoritmo oficial de verificação dos dígitos verificadores.

---

## 📌 Como funciona

O CPF possui 11 dígitos, sendo os dois últimos chamados de **dígitos verificadores**. Eles são calculados a partir dos 9 primeiros dígitos com base em uma fórmula matemática definida pela Receita Federal.

Este projeto implementa exatamente essa fórmula:

1. Remove pontos e traços do CPF digitado (aceita CPF formatado ou só números)
2. Rejeita CPFs com todos os dígitos iguais (ex: `111.111.111-11`)
3. Multiplica os 9 primeiros dígitos por pesos decrescentes (10 a 2)
4. Calcula o primeiro dígito verificador
5. Repete o processo com os 10 dígitos (pesos 11 a 2) para obter o segundo
6. Compara o CPF gerado com o CPF informado

---

## 🚀 Como usar

### Pré-requisitos

- Python 3.x instalado

### Execução

1. Clone o repositório:
```bash
git clone https://github.com/seu-usuario/validador-cpf.git
cd validador-cpf
```

2. Execute:
```bash
python validador_cpf.py
```

3. Digite o CPF quando solicitado (com ou sem formatação):
```
digite seu cpf: 761.952.717-64
```

### Exemplos de saída

```
# CPF válido
761.952.717-64 → 76195271764 é válido

# CPF inválido
digite seu cpf: 111.111.111-11
você enviou dados sequenciais.

digite seu cpf: 00000000000
cpf inválido
```

---

## 🧠 Lógica do algoritmo

```
CPF:  7  6  1  9  5  2  7  1  7  [6][4]
      ×  ×  ×  ×  ×  ×  ×  ×  ×
     10  9  8  7  6  5  4  3  2
     ──────────────────────────
     soma → (soma × 10) % 11 → 1º dígito verificador

Em seguida, repete com pesos 11→2 para o 2º dígito.
```
