# Sobre o projeto

Na construção deste utilizei a última versão estável do Wordpress (5.5) em PT-BR. O tema foi desenvolvido utilizando o tema [**_s** (underscores)](https://github.com/Automattic/_s) como base inicial.

Para acelerar o processo de criação do layout foram utilizados o gulp com rotinas de compilação e minificação dos arquivos SASS e Javascript do tema.

O ambiente utilizado para desenvolvimento foi um PC com Windows 10 rodando PHP 7.3 e MySQL 5.7.

URL local do projeto: http://dasa.test
Login: admin
Senha: 812d6uE@sd8T7BOxfIrJHKKs

# Desempenho

Começando pelo layout, utilizei SASS (na pasta raíz do tema / sass) para gerar o CSS usado pelo tema. Por conta disso, pude criar uma build customizada do Bootstrap de acordo com a identidade visual fornecida por vocês. A build criada contém somente os componentes que foram utilizados para desenvolver o tema em um único arquivo CSS minificado com o tamanho de ~81kb (na pasta raíz do tema / css).

Em relação aos arquivos javascript, eles foram desenvolvidos usando Javascript Puro + jQuery (na pasta raíz do tema / src / js). A rotina programada no gulp minificou e obfuscou o código deixando tudo com ~80kb.

No Wordpress, pelo tema, removi o enqueue de tudo o que era desnecessário para o tema funcionar corretamente (Emojis, Embed etc.) resultando no load de apenas um arquivo javascript (o do tema) e suas dependências (jQuery, jQuery Migrate e Google Maps Api) e dois arquivos CSS (o css do tema e o css carregado pelo Google Fonts).

Foram adicionadas regras de tamanho e corte nas thumbnails das imagens utilizadas nos slides e destaques para que não seja usada uma imagem de tamanho maior que o necessário nestas seções.

Os ícones utilizados no site foram retirados em SVG do arquivo de layout e compilados no CSS do tema, isso facilita o processo de caching (se for necessário ativar), pois não será necessário fazer o request de urls diferentes a cada inserção de ícone.

Nenhum plugin é requerido para o funcionamento do tema.

## Segurança e SEO

Em relação à segurança do tema, as adições de scripts e estilos estão sendo feitas no padrão do Wordpress, pelo enqueue. Todos os inputs de texto, em todas as seções (Widgets, Customizer, etc.), foram sanitizados antes de serem salvos no banco de dados.
Nenhum hook foi alterado de forma que impeça ou execute alguma ação que vá atrapalhar o uso de plugins de proteção/segurança da instalação.

Em relação a SEO, o markup utilizado no tema desenvolvido foi pensando em seguir o máximo  o padrão para indexação, com a hierarquia correta para títulos, conteúdos, imagens, etc. Para renderização de conteúdo, as funções e hooks nativos foram utilizados para facilitar a manipulação por filtros ou plugins de SEO.

## Uso

É possível editar o conteúdo renderizado na página inicial (Slides, Destaques e Lojas) pela Dashboard do Wordpress.

As configurações de redes sociais e texto do rodapé foram adicionadas ao menu "Personalizar" (Customizer) do site, na seção "Configurações do tema".

No rodapé, foram criados widgets que podem ser editados nas seções "Sidebar do final da página principal" e "Barra do Rodapé".

## Observações

Para a localização automática do usuário funcionar, é preciso rodar a instalação Wordpress em protocolo HTTPS.

Como o layout da versão mobile não foi fornecido, adaptei o layout da forma que achei pertinente.

Para recompilar os assets do tema, é necessário instalar as dependências do tema pelo node e rodar um "gulp watch" no terminal.
