# Resumo do programa

<img aligh= "center" alt="phyton" src="https://img.shields.io/badge/Python-14354C?style=for-the-badge&logo=python&logoColor=white"/>

## Tela de cadastro

Cria uma janela simples de login com campos de entrada para "Usuário" e "Senha".
Permite verificar se o login corresponde às credenciais predefinidas.
Fecha a janela ao clicar no "X".
Exibe uma mensagem no terminal ao realizar login com sucesso.




## Importação de módulo 

O PySimpleGUI é uma biblioteca para criar interfaces gráficas de maneira simples e intuitiva.
Importa a biblioteca PySimpleGUI e a referencia com um apelido (sg) para facilitar o uso no

#### from PySimpleGUI import PySimpleGUI as sg  

 ## Configuração do layout

 Define o tema visual da janela. O tema 'Reddit' aplica um conjunto de cores e estilos predefinidos.
 
 ####  sg.theme('Reddit')




##### layout: É uma lista que define a estrutura da interface gráfica.

##### Cada sublista representa uma linha na janela:

##### [sg.Text('Usuário'), sg.Input(key='usuario')]: Cria um texto fixo "Usuário" seguido de um campo de entrada de texto.

##### O parâmetro key='usuario' é usado para identificar o valor digitado neste campo.

##### [sg.Text('Senha'), sg.Input(key='senha', password_char='*')]: Exibe o texto "Senha" e um campo de entrada onde o texto digitado aparece como asteriscos (*), para ocultar a senha.

##### O key='senha' identifica o valor digitado no campo.

##### [sg.Checkbox('Salvar o login?', key='salvar_login')]: Adiciona uma caixa de seleção com o texto "Salvar o login?" - O key='salvar_login' permite verificar se a caixa foi marcada ou não.

##### [sg.Button('Entrar')]: Adiciona um botão com o texto "Entrar".



#### layout = [
    [sg.Text('Usuário'), sg.Input(key='usuario')],
    [sg.Text('Senha'), sg.Input(key='senha', password_char='*')],
    [sg.Checkbox('Salvar o login?', key='salvar_login')],
    [sg.Button('Entrar')]
 
## Criação da Janela

Cria a janela da aplicação, o título da janela é "Tela de login".O layout definido anteriormente é associado à janela.

### janela = sg.Window('Tela de login', layout)

## Loop de eventos 

Este é o loop principal que mantém a janela aberta e interage com o usuário.

##### janela.read(): Retorna dois valores
##### eventos: Identifica a interação do usuário (ex.: botão clicado).
##### valores: Um dicionário que contém os valores dos campos da interface, como os textos digitados ou o estado do checkbox.


### while True:
    eventos, valores = janela.read()

## Fechar a janela

Verifica se o usuário clicou no botão de fechar da janela (ícone de "X").
Se isso acontecer, o break interrompe o loop, encerrando o programa.


    if eventos == sg.WINDOW_CLOSED:
        break


## Verificação do login

#### if eventos == 'Entrar': Verifica se o botão "Entrar" foi clicado.

#### if valores['usuario'] == 'Bruna' and valores['senha'] == '123456': Confere se o nome de usuário digitado é 'jhonatan' e a senha é '123456'.

#### print('Bem-vindo à Dev Learn'): Se as credenciais estiverem corretas, exibe a mensagem no terminal.
    
    
        if eventos == 'Entrar':
        if valores['usuario'] == 'jhonatan' and valores['senha'] == '123456':
            print('Bem-vindo à Dev Learn')




