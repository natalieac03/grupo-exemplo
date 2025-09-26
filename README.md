# Agente Gerador de Questões de Matemática  

## Equipe  
| Nome | GitHub |
| :--- | :--- |
| Natalie Coelho | [@natalieac03](https://github.com/natalieac03) |
| Gabriel Marques | [@Gabrielllaer](https://github.com/Gabriellaer) |
| Gabriel Taveira | [@Gstaveira](https://github.com/Gstaveira) |
| João Constantino | [@usuario](https://github.com/usuario) |
| Lara Srva | [@usuario](https://github.com/usuario) |

## Visão Geral  

O **Agente Gerador de Questões de Matemática** é uma aplicação de Inteligência Artificial projetada para auxiliar educadores na criação de questões de matemática personalizadas, alinhadas à **BNCC**.  
Ele interpreta solicitações do usuário, utiliza ferramentas Python para gerar gráficos e tabelas, e produz questões completas em formato JSON, incluindo enunciado, alternativas, resposta correta e explicação detalhada.  

## Como Usar  

Digite sua solicitação na caixa de texto seguindo os campos separados por vírgula:  
- `habilidade_bncc:` código e descrição da habilidade BNCC.  
- `nivel_dificuldade:` fácil, médio ou difícil.  
- `quantidade:` número de questões (até 10).  
- `tipo_questao:` multipla_escolha ou dissertativa.  
- `observacao:` (opcional) instruções extras.  

**Exemplo:**  
```text
habilidade_bncc:(EM13MAT102) Analisar tabelas e gráficos..., nivel_dificuldade: difícil, quantidade: 3, tipo_questao: multipla_escolha
```

## Funcionamento Técnico  

- **Modelo:** `Qwen/Qwen2.5-VL-32B-Instruct` ([Hugging Face](https://huggingface.co/Qwen/Qwen2.5-VL-32B-Instruct))  
- **Janela de contexto:** até 32.768 tokens.  
- **Parâmetros de geração:** `max_tokens=4096`, `temperature=0.6`.  
- **Prompt principal:** definido em `prompts.yaml` (~3000 tokens).  
- **Ferramentas Python:** permitem gerar gráficos e tabelas.  
- **Saída:** objeto Python (lista de dicionários compatível com JSON).  
- **Visualização:** o Gradio renderiza as questões e exibe gráficos, quando presentes.  
