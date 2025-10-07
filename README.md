# Super-senha

Super-senha é uma aplicação desktop em Java, com interface gráfica, que utiliza informações do próprio sistema (data e hora) e uma fórmula matemática para gerar uma senha dinâmica e robusta, conhecida como "Super Senha".

## Como funciona a geração da Super Senha?

A lógica central de geração da senha utiliza informações do sistema local (dia, mês, ano e hora atuais) e as aplica na seguinte fórmula:

```
SuperSenha = ((Dia + Mês) × Ano) + Hora
```

- **Dia:** Dia atual do sistema (entre 1 e 31)
- **Mês:** Mês atual do sistema (entre 1 e 12)
- **Ano:** Ano atual do sistema (quatro dígitos)
- **Hora:** Hora atual do sistema (formato 24 horas)

Opcionalmente, o usuário pode aplicar pequenos ajustes à senha final, como subtrair 1 ou 2, dependendo das opções selecionadas na interface.

Exemplo:  
Se a data e hora do sistema forem 7 de outubro de 2025, às 16h:
- Dia = 7
- Mês = 10
- Ano = 2025
- Hora = 16

Aplicando a fórmula:  
SuperSenha = ((7 + 10) × 2025) + 16 = (17 × 2025) + 16 = 34.425 + 16 = **34.441**

## Estrutura do Projeto

```
├── build.xml          # Script de build (Ant)
├── manifest.mf        # Manifesto da aplicação Java
├── src/
│   ├── Classes/       # Lógica de geração de senha
│   └── Formularios/   # Telas e formulários (interface gráfica)
├── test/              # Telas de teste e exemplos de uso
├── build/             # Arquivos gerados na build
├── dist/              # Distribuição final da aplicação
└── nbproject/         # Configurações do NetBeans
```

## Requisitos

- Java JDK 8 ou superior
- Ant (para compilar via build.xml)
- NetBeans (opcional, para desenvolvimento e execução)

## Como executar

1. Clone este repositório:
   ```sh
   git clone https://github.com/romilsonx/Super-senha.git
   ```
2. Compile usando Ant:
   ```sh
   ant clean
   ant jar
   ```
3. Execute o arquivo `.jar` gerado na pasta `dist/`:
   ```sh
   java -jar dist/Super-senha.jar
   ```

## Interface

A aplicação possui uma interface gráfica simples, onde o usuário pode:
- Gerar a Super Senha usando a data e hora do sistema
- Aplicar ajustes opcionais à senha
- Limpar o campo de senha
- Visualizar informações sobre o funcionamento da fórmula

## Observações de Segurança

- **Atenção:** A senha gerada é determinística e baseada em informações públicas do sistema. Não é indicada para cenários críticos de segurança ou autenticação sensível.
- Ideal para uso em exercícios didáticos, sistemas de acesso temporário ou como base para aprimoramentos.

## Licença

Projeto sob licença MIT.

---

> Desenvolvido por Romilson dos Santos.  
> Para sugestões ou dúvidas, abra uma issue ou entre em contato pelo GitHub.
