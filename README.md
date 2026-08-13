<div align="center">
  
# Backend Developer

### Designing scalable, reliable systems — across domains.

I build and maintain backend applications and services in **Java** and **TypeScript**, focused on writing clean, well-tested, and maintainable code that solves real business problems.

![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=spring-boot&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![NestJS](https://img.shields.io/badge/NestJS-E0234E?style=for-the-badge&logo=nestjs&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
</div>

---

## 👋 About Me

I'm a **backend developer** always learning and improving. My portfolio spans **fintech and payments, identity and access control, inventory and order management, and logistics automation**, with projects covering REST APIs, async processing, caching, and system integrations.

I have hands-on operational experience inside large-scale Distribution Centers, which taught me to understand problems from the business side and communicate well with non-technical people. That background shapes how I work today: **pragmatic solutions, clean code, and software that actually gets used**.

I work daily with **integration APIs**, **backend services**, and **event-driven flows** in **Java and TypeScript** — and I built **BuildFlow System**, a solo project that integrates business management and logistics, which I license to local businesses currently using it in production.

---

## 🛠️ Tech Stack

### Backend

| Technology | Applications |
|------------|--------------|
| **Java 17+** | REST APIs, microservices, integrations |
| **Spring Boot** | Spring Data, Security, MVC, integrations |
| **TypeScript** | Typed APIs, robust integrations |
| **Node.js** | High-performance APIs, microservices |
| **NestJS** | Modular architecture, integrations |

### Systems & Architecture

```yaml
Distributed Systems:
  - Event-driven architecture
  - Message queues and async processing
  - Caching strategies (cache-aside, TTL, eviction)
  - Rate limiting and API protection

Resilience:
  - Idempotency and retry with backoff
  - Transaction control and consistency
  - Job scheduling and delayed execution
```

### Identity, Security & Payments

```yaml
Identity & Access:
  - Authentication and authorization
  - API key management
  - Permissions and scopes

Payments & Fintech:
  - Payment processing and validation
  - Double-entry ledgers
  - Fraud detection
  - Digital wallets and banking APIs
```

### Databases & ORM

```yaml
SQL:
  - PostgreSQL (primary)
  - MySQL / MariaDB
  - Query optimization
  - Stored procedures

ORM / Frameworks:
  - Spring Data JPA / Hibernate
  - Prisma ORM
  - TypeORM
```

### Tools & DevOps

- **Version control:** Git, GitHub Flow
- **Testing:** JUnit, Mockito, Jest
- **Containers:** Docker, Docker Compose
- **APIs:** RESTful, Webhooks, Event-driven
- **Monitoring:** Logging, Actuator, PM2

---

## 🚀 Featured Projects

### Fintech & Payments

| Project | Highlights |
|---------|-----------|
| [**idempotent-payment-api**](https://github.com/your-username/idempotent-payment-api) | Idempotency keys to prevent duplicate charges, atomic transaction control |
| [**event-driven-payment-system**](https://github.com/your-username/event-driven-payment-system) | Async messaging for decoupled services, reliable delivery and retries |
| [**financial-ledger**](https://github.com/your-username/financial-ledger) | Double-entry ledger tracking transactions and account balances |
| [**fraud-detection-processor**](https://github.com/your-username/fraud-detection-processor) | Detects suspicious financial transactions in real time |

### Distributed Systems & Infrastructure

| Project | Highlights |
|---------|-----------|
| [**url-shortener**](https://github.com/your-username/url-shortener) | Caching for high-read throughput, click analytics, rate limiting |
| [**distributed-cache-service**](https://github.com/your-username/distributed-cache-service) | Cache-aside with eviction policies, horizontal scalability |
| [**job-processing-system**](https://github.com/your-username/job-processing-system) | Async queues with retries and backoff, scheduling, idempotent processing |
| [**rate-limit-service**](https://github.com/your-username/rate-limit-service) | Protects APIs from excessive traffic |

### Identity & Access Control

| Project | Highlights |
|---------|-----------|
| [**identity-service**](https://github.com/your-username/identity-service) | Authentication and authorization for backend applications |
| [**api-key-management**](https://github.com/your-username/api-key-management) | API keys with permissions, auth and rate limiting |

### Products & Platforms

| Project | Highlights |
|---------|-----------|
| [**ERP_BuildFlow_Demo**](https://github.com/your-username/ERP_BuildFlow_Demo) | Solo project — WMS, ERP, inventory and billing platform, licensed to and used by local businesses |
| [**subscription-management-service**](https://github.com/your-username/subscription-management-service) | Plans, billing cycles, renewals and subscription lifecycle |

---

## 💻 Code Quality

```java
// Example: idempotent payment processing

@Service
public class PaymentService {

    @Transactional
    public PaymentResult process(ProcessPaymentRequest request) {
        if (paymentRepository.existsByIdempotencyKey(request.getIdempotencyKey())) {
            return PaymentResult.replay();
        }

        Payment payment = paymentRepository.save(
            Payment.pending(request)
        );

        try {
            gateway.charge(payment);
            payment.confirm();
        } catch (GatewayException e) {
            payment.fail();
            throw new PaymentRetryableException(e);
        }

        return PaymentResult.success(payment);
    }
}
```

```typescript
// Example: distributed job processing with retries

@Injectable()
export class JobProcessorService {

  async processJob(job: Job): Promise<JobResult> {
    const attempts = job.metadata.attempts ?? 0;
    const maxAttempts = this.config.getMaxRetries(job.type);

    try {
      const result = await this.handlers.execute(job);
      return await this.jobStore.complete(job.id, result);
    } catch (error) {
      if (attempts >= maxAttempts) {
        await this.jobStore.fail(job.id, error);
        return JobResult.failed();
      }

      await this.jobQueue.scheduleRetry(job, {
        attempt: attempts + 1,
        delay: this.backoff.delay(attempts),
      });

      return JobResult.retrying();
    }
  }
}
```

---

## 🎓 Education

- **B.Sc. Software Engineering** — in progress

---

## 📫 Let's Connect
- **LinkedIn:** [Roberto Carlos](https://linkedin.com/in/robertobarbosa-rc)
- **Email:** [robertobarbosa.osg@gmail.com](robertobarbosa.osg@gmail.com)

---

<div align="center">

> "I don't just write code. I build software that solves real problems."

**⭐ BuildFlow System — in use by local businesses** · **⚙️ Distributed systems** · **🔐 Identity & security** · **💳 Fintech & payments**

</div>
