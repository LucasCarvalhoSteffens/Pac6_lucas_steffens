# Análise Técnica de Projetos Reais no GitHub

**Nome do arquivo:** `pac6_github_lucas.md`  
**Aluno:** Lucas  
**Disciplina:** Engenharia de Software  
**Entrega:** 23/06  

## Objetivo

Este exercício tem como objetivo exercitar a análise técnica aplicada, desenvolvendo a capacidade de reconhecer boas práticas de arquitetura e construção de software em projetos reais de código aberto.

---

## Características Técnicas Identificadas

### ✅ Autenticação com JWT/OAuth  
**Projeto:** [django-rest-framework](https://github.com/encode/django-rest-framework)  
**Trecho de código:**
```python
from rest_framework_simplejwt.authentication import JWTAuthentication

class CustomView(APIView):
    authentication_classes = [JWTAuthentication]
```
**Justificativa:**  
JWT garante autenticação segura e stateless em APIs REST. É ideal para aplicações distribuídas e muito comum em APIs modernas.

---

### ✅ Testes automatizados (unitários e integração)  
**Projeto:** [realworld](https://github.com/gothinkster/realworld)  
**Trecho de código:**
```javascript
describe('POST /users/login', () => {
  it('should login an existing user', () => {
    // código de teste
  });
});
```
**Justificativa:**  
Cobertura de testes ajuda a manter a estabilidade do projeto durante mudanças e refatorações.

---

### ✅ Uso de cache (Redis)  
**Projeto:** [nestjs-realworld-example-app](https://github.com/lujakob/nestjs-realworld-example-app)  
**Trecho de código:**
```typescript
imports: [
  CacheModule.register({
    store: redisStore,
    host: 'localhost',
    port: 6379,
  }),
]
```
**Justificativa:**  
O cache reduz chamadas repetidas ao banco de dados, melhorando o desempenho da aplicação.

---

### ✅ Filas de mensageria (Kafka)  
**Projeto:** [microservices-demo](https://github.com/GoogleCloudPlatform/microservices-demo)  
**Trecho de código:**
```yaml
containers:
  - name: kafka
    image: wurstmeister/kafka
```
**Justificativa:**  
Kafka permite o desacoplamento entre sistemas e a distribuição de carga com segurança e tolerância a falhas.

---

### ✅ Circuit Breaker  
**Projeto:** [resilience4j](https://github.com/resilience4j/resilience4j)  
**Trecho de código:**
```java
CircuitBreaker circuitBreaker = CircuitBreaker.ofDefaults("backendService");
CheckedFunction0<String> decoratedSupplier = CircuitBreaker
    .decorateCheckedSupplier(circuitBreaker, backendService::call);
```
**Justificativa:**  
Evita falhas em cascata e protege o sistema de sobrecarga em chamadas de serviços externos.

---

### ✅ CI/CD com pipelines  
**Projeto:** [fastapi](https://github.com/tiangolo/fastapi)  
**Trecho de código (.github/workflows/test.yml):**
```yaml
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - name: Run Tests
        run: pytest
```
**Justificativa:**  
A integração contínua ajuda a identificar falhas antes que sejam publicadas, mantendo a confiabilidade do software.

---

### ✅ Análise estática de código  
**Projeto:** [sentry](https://github.com/getsentry/sentry)  
**Trecho de código:**
```yaml
- name: Lint with flake8
  run: |
    flake8 .
```
**Justificativa:**  
Detecta problemas antes da execução e mantém padrões de qualidade no código.

---

### ✅ Serverless/Lambda  
**Projeto:** [serverless-stack](https://github.com/serverless-stack/serverless-stack)  
**Trecho de código:**
```yaml
functions:
  getUser:
    handler: functions/get-user.handler
```
**Justificativa:**  
Permite execução sob demanda com escalabilidade automática e economia de recursos.

---

## 📄 Documento PDF

Você pode acessar o relatório completo em PDF no arquivo `pac6_github_lucas.pdf` incluído neste repositório.

## 🛠️ Tecnologias Exploradas

- Redis
- RabbitMQ / Kafka
- JWT / OAuth2
- GitHub Actions
- Circuit Breaker (Resilience4j)
- Serverless Framework
- SonarQube / Flake8
- Jest / Pytest

## ✅ Conclusão

Esta análise técnica permitiu estudar boas práticas usadas em projetos populares, reforçando conceitos de arquitetura moderna, escalabilidade, resiliência e segurança no desenvolvimento de software.
