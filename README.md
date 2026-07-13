<div align="center">

# Software Developer | Logistics Tech Specialist
### Java • Spring Boot • TypeScript • Node.js • TOTVS • WMS

<img src="https://cdn.pfps.gg/banners/5480-dark-aesthetic-anime.png" alt="Banner de Desenvolvimento" style="width: 100%; max-height: 120px; object-fit: cover; border-radius: 8px;"/>

![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=spring-boot&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![TOTVS](https://img.shields.io/badge/TOTVS-003366?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI+PHBhdGggZmlsbD0id2hpdGUiIGQ9Ik0xMiAyQzYuNDggMiAyIDYuNDggMiAxMnM0LjQ4IDEwIDEwIDEwIDEwLTQuNDggMTAtMTBTMTcuNTIgMiAxMiAyem0wIDE4Yy00LjQxIDAtOC0zLjU5LTgtOHMzLjU5LTggOC04IDggMy41OSA4IDgtMy41OSA4LTggOHoiLz48L3N2Zz4=&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)

**Construindo pontes entre operação logística e tecnologia**

</div>

---

## 🎯 Sobre Mim

**Desenvolvedor de Software e Especialista em Logística** com ampla experiência em operações de grandes Centros de Distribuição.

Minha carreira foi construída entre a **operação e a tecnologia**. Antes de desenvolver soluções, vivi na prática os desafios da armazenagem, inventário, separação, expedição e gestão logística de ponta a ponta. Essa experiência me permite enxergar problemas além do código e construir soluções alinhadas à realidade do negócio.

Atuo no desenvolvimento de **APIs de integração com sistemas TOTVS**, conectando ERPs (Protheus/RM) a soluções de WMS, TMS e automação logística. Trabalho diariamente com backend em **Java e TypeScript**, construindo pontes eficientes entre o mundo TOTVS e outras plataformas.

Minha estratégia para entregar excelência é sustentada por uma base acadêmica única: **formado em Ciência da Computação** e atualmente curso **Engenharia da Produção**. Combinação que me permite dominar tanto a engenharia de software quanto a otimização de processos.

**Sou especialista em WMS e ERP** e fundador do **BuildFlow System**, uma plataforma própria que integra gestão empresarial e logística em um único ecossistema, atualmente em operação e gerando resultados reais para seus usuários.

---

## 🛠 Stack Técnica

### **Backend Principal**

| Tecnologia | Nível | Aplicações |
|------------|-------|-------------|
| **Java 17+** | Avançado | APIs REST, integrações TOTVS, microsserviços |
| **Spring Boot** | Avançado | Spring Data, Security, MVC, integrações |
| **TypeScript** | Avançado | APIs tipadas, integrações robustas |
| **Node.js** | Avançado | APIs performáticas, microservices |
| **NestJS** | Intermediário | Arquitetura modular, integrações |

### **Integrações & ERPs**

```yaml
TOTVS Ecossistema:
  - TOTVS Protheus (integrações via REST/AdvPL)
  - TOTVS RM (API de integração)
  - Conexão com WMS e TMS
  - Automação logística

Sistemas de Gestão:
  - WMS (Warehouse Management)
  - ERP (Enterprise Resource Planning)
  - TMS (Transport Management)
```

Banco de Dados & ORM

```yaml
SQL:
  - PostgreSQL (principal)
  - MySQL / MariaDB
  - Query optimization
  - Stored procedures

ORM/Frameworks:
  - Spring Data JPA / Hibernate
  - Prisma ORM
  - TypeORM
```

Ferramentas & DevOps

· Controle de versão: Git, GitHub Flow
· Testes: JUnit, Mockito, Jest
· Containers: Docker, Docker Compose
· APIs: RESTful, Webhooks, Event-driven
· Monitoramento: Logging, Actuator, PM2

---

📁 Projetos em Destaque

BuildFlow System (Fundador & Tech Lead)

Java • Spring Boot • TypeScript • NestJS • PostgreSQL

· Plataforma completa que integra gestão empresarial e logística em um único ecossistema
· Módulos: WMS, ERP, estoque, faturamento, fiscal
· APIs de integração com TOTVS Protheus e RM
· Atualmente em operação com usuários reais

API de Integração TOTVS Protheus → WMS

Java • Spring Boot • REST APIs • AdvPL

· Bridge entre ERP Protheus e soluções de WMS
· Sincronização bidirecional de: produtos, estoque, pedidos, notas fiscais
· Tratamento de filas e retentativas para alta disponibilidade
· Redução de 70% no tempo de processamento de pedidos

Middleware para Automação Logística

TypeScript • Node.js • Express • PostgreSQL

· Central de roteirização de separação e expedição
· Integração com coletores RF e impressoras de etiquetas
· Relatórios de performance operacional em tempo real
· Processamento de 5k+ pedidos/hora

---

💻 Código com Qualidade

```java
// Exemplo: Integração com TOTVS Protheus

@RestController
@RequestMapping("/api/totvs/integration")
@RequiredArgsConstructor
public class TotvsIntegrationController {
    
    private final TotvsClient totvsClient;
    private final WmsService wmsService;
    
    @PostMapping("/sync/orders")
    public ResponseEntity<SyncResult> syncOrders(
        @RequestBody SyncRequest request
    ) {
        // Busca pedidos no Protheus via API
        List<Order> orders = totvsClient.fetchOrders(request.getLastSync());
        
        // Transforma e envia para WMS
        SyncResult result = wmsService.processOrders(orders);
        
        return ResponseEntity.ok(result);
    }
}
```

```typescript
// Exemplo: Middleware logístico com NestJS

@Injectable()
export class PickingOptimizerService {
  
  async optimizePickingRoute(orders: Order[]): Promise<OptimizedRoute> {
    // Algoritmo baseado em experiência real de CD
    const zones = this.groupByZone(orders);
    const priority = this.calculatePriority(zones);
    const route = this.generateOptimalPath(priority);
    
    return {
      estimatedTime: route.duration,
      sequence: route.steps,
      efficiency: this.calculateEfficiency(route)
    };
  }
}
```

---

🎓 Formação Acadêmica

· Ciência da Computação - (Concluído)
· Engenharia da Produção - (Cursando)

---

<div align="center">

"Não construo apenas software. Construo pontes entre a operação que vivi e a tecnologia que domino."

⭐ BuildFlow System - Em operação
🚚 Especialista em logística operacional
📦 WMS | ERP | TOTVS

</div>
