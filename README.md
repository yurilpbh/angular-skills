# Angular Skill Test

![Resultado do teste](/images/GifProject.gif)

Projeto em angular 8 para a apresentação de um dashboard com as skills pessoais.

Atividades

* 1. Responsividade do Dashboard de Skills
    
    Ajustar o layout dos cards de forma responsiva, para exibir em telas com breakpoint lg ou maior com 3 cards por linha, breakpoint md com 2 cards por linha, e menores que md com 1 card por linha.
    Referência dos breakpoints: https://github.com/angular/flex-layout/wiki/Responsive-API.

        -Para implementar esse ajuste foram alterados os arquivos "dashboard.*"

* 2. Funcionalidades do Card

    - A cada click no botão like, incrementar um contador e exibir a quantidade de likes
        ```javascript
        this.card.likes = card.likes + 1;
        ```
        - esse contador deve ser incrementado e salvo via api rest (pode utilizar a api do httpClient)
        ```javascript
        this.httpClient.put<number>('/api/skills/'+this.card.id, this.card).subscribe();
        ```
        - após o incremento de likes chegar no valor 5, deve ficar azul
        ```javascript
        if(this.card.likes == 5){
        document.getElementsByTagName("button")[this.card.id*2 -2].style.backgroundColor = "blue"
        }
        ```    
        - após o incremento de likes chegar em um valor maior que 10, escolha uma cor de sua preferencia que não seja nem preto nem azul.
        ```javascript
        if(this.card.likes > 10){
        document.getElementsByTagName("button")[this.card.id*2 -2].style.backgroundColor = "red"
        }
        ```
        - uma api rest já está integrada usando o https://github.com/angular/in-memory-web-api. Está configurado um delay de 5 segundos. 
        Por isso, implemente também algum tipo de loading amigável para informar o usuário do processamento da requisição.
            - Implementei uma animação simples de entrada de loading. "Roll-in-left" no arquivo "animation.css" dentro da pasta "card".
    - no botão share, abrir uma nova aba no seu linkedin.
    ```javascript
    window.open("https://www.linkedin.com/in/yurilpbh");
    ```

* 3. Design

    Essa tela está bem sem graça não? Bom, ta aí a chance de você mostrar seus dotes artísticos !
    Afinal, queremos encantar nossos clientes com a apresentação dessas skills, portanto seja criativo, e fique a vontade para adicionar animações, cores, bordas, enfim, o que achar melhor para que essa tela fique mais a sua cara.
    
        - Adicionei diversas mudanças em vários arquivos a fim de deixa a interface para o usuário mais atrativa.
