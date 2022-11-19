# Cloud-Parking API

Projeto entregue como atividade final do **Bootcamp Québec Java Digital** da Digital Innovation One.

Consiste numa API que, ligada a um banco de dados PostgreSQL, permite o registro de entrada e saída de veículos em um estacionamento.

Foram utilizadas as seguintes dependências, sendo a maioria do Spring Framework/Spring Boot:

- Spring Web;
- Spring Dev Tools
- Spring Security
- Spring Data JPA
- Swagger;
- ModelMapper;
- RestAssured;
- Test Containers.

## CORS e Proteção CRFS no Spring Security
Um desafio inesperado foi que, após seguir as instruções do professor para a eleboração da aplicação, foi observado um erro constante que se repetia toda vez que era tentado fazer um POST, UPDATE ou DELETE. Mesmo copiando o código no repositório do professor, o erro persistia, de forma que só era possível fazer requisições GET, todas as outras retornavam *status code <401\>*.

Após pesquisar mais sobre o erro, verificou-se que o problema era que o Spring Security vem habilitado por padrão com proteção contra CSRF, que estaria interferindo nas requisições. Assim, graças às informações obtidas nesse [post do stackoverflow](https://stackoverflow.com/questions/50486314/how-to-solve-403-error-in-spring-boot-post-request) foi possível solucionar o problema. Não é uma solução ideal, pois retira uma proteção importante da API, mas para os fins da atividade era a melhor possível.

Após a remoção de tal restrição, todo o código passou a funcionar como esperado.