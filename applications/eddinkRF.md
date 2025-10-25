# Eddink - Retroactive Public Goods Funding Platform

- **Team Name:** Eddink Team
- **Payment Address:** Polkadot: 14AhXypHDjzMQ3FyYsvTDtwGBfukAVET43N43FYsZmTjXf3n


## Project Overview :page_facing_up:

### Overview

## Vision: The Future of Decentralized Public Goods Funding

Eddink represents a practical approach to retroactive public goods funding, transforming the traditional grant-making process into a transparent, community-driven, and algorithmically-enhanced platform. By combining cutting-edge ink! smart contract technology with battle-tested funding mechanisms learned from Optimism’s 4-year evolution, we’re creating the foundation of a sophisticated retroactive funding platform native to the Polkadot ecosystem.

Every community member should be able to create funding rounds for causes they care about, where projects are evaluated through transparent, algorithmic processes, and where impact is rewarded after it’s been demonstrated, as famously said “It’s easier to agree on the impact of a project based on what they have already done” Each funding cycle becomes not just a distribution mechanism, but a catalyst for ecosystem growth and innovation.

## Why “Eddink”? The Philosophy Behind Permanent Impact

The name “Eddink” combines **Edding markers** (permanent, indelible) with **ink!** (ink! smart contract language), symbolizing our vision of creating permanent, lasting impact through decentralized funding mechanisms.

Just as an Edding marker creates marks that endure, Eddink creates funding decisions that are transparent, immutable, and designed to generate lasting positive impact. This retroactive funding platform serves as the foundation for our broader ambitions: building toward a future where sustainable, community-driven funding mechanisms can support real-world volunteer initiatives and social good—starting with the proven, manageable scope of digital public goods in the Polkadot ecosystem.

### Ink! Ecosystem Impact

Eddink directly addresses a critical gap in the ink! and Polkadot ecosystem: **sustainable, transparent funding for public goods**. The platform will:

**Drive ink! Smart Contract Adoption:**
- Showcase advanced ink! v6 capabilities through real-world financial infrastructure
- Provide a reference implementation for complex multi-contract systems
- Demonstrate ink!'s suitability for governance and funding mechanisms
- Create reusable contract modules for the community (voting systems, fund distribution, project registries)

**Strengthen Ecosystem Infrastructure:**
- Establish transparent funding mechanisms for ink! tooling, libraries, and educational content
- Enable community-driven resource allocation without central gatekeepers
- Create sustainable incentives for developers building public goods
- Foster cross-parachain collaboration through standardized funding rounds

**Generate Demonstrable Business Value:**
- Validated by Optimism's evolution showing >1.0 revenue-to-grant ratios in mature rounds
- Platform fees and premium features provide sustainable operational model
- Incentivize projects that generate ecosystem value (increased TVL, developer activity, transaction volume)
- Create positive feedback loops where funded projects contribute back to the ecosystem

**Enable Community Empowerment:**
- Any community member can create funding rounds for causes they care about
- Transparent, on-chain evaluation criteria reduce subjective bias
- Badge-holder model ensures informed decision-making while maintaining decentralization
- Foundation for future algorithmic evaluation and quadratic funding mechanisms

**Production Readiness & Future Growth:**
- Built for immediate production use with clear sustainability model
- Modular architecture enables seamless upgrades (QF integration, cross-chain expansion, algorithmic evaluation)
- Open-source codebase serves as educational resource and reference implementation
- Designed to scale from initial dozens of projects to thousands as ecosystem matures

# Technical Architecture & User Experience

## Platform Architecture

**CATEGORY:** ink! DApp / Public Goods Infrastructure

**Technology Stack:**

- **Smart Contracts:** ink! v6 with modular funding mechanisms, upgradable via Polkadot governance
- **Frontend:** React/Next.js with Polkadot.js integration for wallet connectivity and on-chain interactions
- **Backend:** Node.js with PostgreSQL for off-chain data indexing (e.g., project descriptions, media links) and API services
- **Authentication:** Polkadot wallet integration (Substrate/EVM accounts) with GitHub OAuth for identity verification
- **Infrastructure:** IPFS for decentralized storage of application materials, dedicated indexing services for transparent data access

### Core Design Principles from Optimism’s Evolution

Our model draws on the lessons of Optimism’s retrofunding evolution while tailoring to Polkadot’s data-rich environment:

- **Voting-Based Foundations with Algorithmic Readiness:** This grant’s scope focuses on structured, badge-holder–driven round voting while laying the technical foundation for future algorithmic evaluation modules. By prioritizing transparency in data collection and evaluation logic now, the transition to algorithmic retrofunding will be seamless and scalable later.
- **Sybil-Resistant Trusted Actor Model:** Identity and validation rely on Polkadot-native primitives for badge holders, enabling integrity during early voting-based rounds and forming the trust layer for later algorithmic aggregation. Projects creators would also need to prove owning the Github repos of their project
- **Gaming Resistance (Future-Ready):** The architecture accommodates multiple evaluators and eventually multiple competing algorithms, which together will resist manipulation as the system scales.

## Progressive Platform Evolution

We designed the platform to evolve naturally as community capacity and data maturity increase:

- **Initial Access:** Simple retrofunding rounds with badge-holder voting and transparent evaluation data.
- **Enhanced Capabilities:** Introduction of algorithmic evaluation tools and weighted voting as data integrity and trust primitives solidify.
- **Full Platform Access:** Integration of quadratic funding, algorithmic scoring modules, and cross-chain coordination for ecosystem-scale retrofunding.

### Core Data Models & API Specifications

**Smart Contract Data Models:**

```rust
// Project Registry
type ProjectId = u64;
type RoundId = u64;
type VoteCount = u128;
struct Project {
    id: ProjectId,
    owner: AccountId,
    github_verification: bool,
    metadata_hash: Hash,  // IPFS link to full details
    created_at: Timestamp,
    verification_status: VerificationStatus,
}

// Funding Round
struct Round {
    id: RoundId,
    admin: AccountId,
    total_funds: Balance,
    voting_start: Timestamp,
    voting_end: Timestamp,
    eligible_projects: Vec<u64>,
    badge_holders: Vec<AccountId>,
    status: RoundStatus,
}

// Vote Allocation
struct VoteAllocation {
    badge_holder: AccountId,
    round_id: u64,
    allocations: Vec<(ProjectId, VoteCount)>,
    timestamp: Timestamp,
}
```

**REST API Endpoints (Backend):**
- `POST /api/projects` - Register new project
- `GET /api/projects/:id` - Retrieve project details
- `POST /api/rounds` - Create funding round
- `GET /api/rounds/:id` - Get round details and participants
- `POST /api/votes` - Submit badge holder vote
- `GET /api/analytics/project/:id` - Project impact metrics
- `GET /api/analytics/round/:id` - Round statistics

### What This Project Will NOT Provide

To manage expectations and scope clearly:

- **Automated Impact Measurement:** Initial version focuses on badge-holder voting; algorithmic impact scoring is planned for future iterations
- **Fiat Currency Integration:** Platform operates exclusively with DOT and parachain tokens; no fiat on/off ramps
- **Legal Compliance Management:** Projects are responsible for their own legal, tax, and regulatory compliance
- **Dispute Resolution System:** No built-in arbitration mechanism; relies on community governance and transparent criteria
- **Token Streaming:** While the architecture supports future integration, continuous payment streams are not part of the initial scope
- **Cross-Chain Deployment:** Initial launch focuses on Polkadot Asset Hub; expansion to other parachains comes in later phases
- **Sybil Resistance Beyond Badge Holders:** Advanced identity verification (e.g., humanity proofs) planned for future, not initial scope
- **Marketing or Business Development Services:** Platform provides funding infrastructure only; project promotion is self-driven

### Business Model & Economic Sustainability

**Revenue Streams:**
- **Platform Fees:** 1-2% fee on funds to cover operational costs recieved from the round creater and additional funding members. We will not charge anything from the end distributed amount to the teams
- **Premium Features:** (Future) Advanced analytics, private rounds, custom branding for DAOs/enterprises
- **Treasury Grants:** Potential future support from Polkadot Treasury as recognized public goods infrastructure ane expansion

**Target Market:**
- Primary: Polkadot/ink! developers building public goods (tooling, infrastructure, education)
- Secondary: Parachain teams seeking to fund ecosystem growth
- Tertiary: DAOs and community organizations requiring transparent funding mechanisms

**Scalability & Growth:**
- Modular architecture enables horizontal scaling across parachains
- Open-source model reduces development costs while increasing adoption
- Target >1.0 revenue-to-grant ratio within 2 years (based on Optimism's evolution)
- Self-sustaining operational model through collected fees and community contributions

### Future Production Plans

**Phase 1 - Foundation (Months 1-6 post-launch):**
- Deploy on Polkadot Asset Hub mainnet
- Onboard initial 20+ funding rounds
- Establish 200+ verified badge holders
- Distribute $100K+ through platform
- Achieve 99.5%+ uptime

**Phase 2 - Community Integration (Months 7-18):**
- Integrate algorithmic evaluation tools
- Deploy quadratic funding mechanisms
- Expand to 3+ additional parachains
- Achieve operational sustainability (>1.0 revenue ratio)
- Establish community governance for platform parameters

**Phase 3 - Scale & Sophistication (Months 19+):**
- Full algorithmic evaluation marketplace
- Cross-chain fund coordination via XCM
- Advanced identity and sybil resistance
- Support 1,000+ projects annually
- Complete transition to community ownership

---

## Development Overview

## The Eddink! Platform Vision

Eddink moves deliberately from a conceptual framework inspired by Optimism’s RF evolution toward a **foundation-first implementation** for Polkadot’s public goods ecosystem. This grant scope emphasizes building **the essential primitives for community-driven retrofunding**, while the groundwork for **algorithmic scalability** is designed in parallel.

## What We’ve Already Done

- **Research Foundation:** Based on comprehensive analysis of Optimism’s Seasons 4–8, OpenSourceObserver insights, and Atlas App architecture, we identified key success mechanics for transparency, bias reduction, and scalable impact measurement.
- **Bias Reduction & Scalability:** Transitioning from subjective votes to metrics, then algorithms, reduces bias and enables funding across hundreds of projects as data integration matures.
- **Economic Sustainability:** Evidence from Optimism’s journey demonstrates retrofunding’s potential to yield sustainable public goods funding ratios (>1.0 revenue-to-grant), validating Eddink’s model.

## What Happens During the Grant Scope

This grant focuses on the foundational RetroFunding Infra that is needed for the more scalable algorithmic RetroFunding Mechanism/

**Phase 1 (Weeks 1–4):** Build foundation for projects, rounds, and badge-holder voting

**Phase 2 (Weeks 5–8):** Implement the first version of evaluation UI elements, and the FrontEnd

**Phase 3 (Weeks 9–12):** System integration, testing, and validation of round logic and data transparency pipelines

---

## Development Status :open_book:

**Research Foundation:**
- Comprehensive analysis of Optimism's RetroFunding Seasons 4-8 evolution documented and shared with research community
- Research paper on "Adaptive Platform for Incentivizing Pro-Environmental Behavior" published on ResearchGate (https://www.researchgate.net/publication/395004196)
- Insights from OpenSourceObserver and Atlas App architecture integrated into platform design

**Prior Work & References:**
- **Sustained Platform:** Winner of Web3 Summit 2025 Quadratic Funding Bounty using ink! - demonstrates team's capability with ink! smart contracts and funding mechanisms (https://github.com/prgprg/qf_front, https://sustained-aachen.vercel.app/)
- **PrivaCT:** Winner of Celestia's Mammothon - showcases team's ability to deliver production-ready blockchain applications (https://github.com/Aghostraa/PrivaCT)
- **Prompt Genius:** Blockscout Track Winner at ETHGlobal Prague - demonstrates frontend and smart contract integration expertise (https://ethglobal.com/showcase/prompt-genius-tv801)

**Community Engagement:**
- A member of the team has already participated in multiple public goods rounds namely Optimism's RPGF 3 as project applicant, gaining firsthand insight into retrofunding mechanisms
- Active contributor to growthepie analytics platform, focusing on contract labeling and Open Labels Initiative
- Presented research findings at blockchain conferences and academic forums

**Technical Foundation:**
- Team has delivered production quadratic funding infrastructure using ink! smart contracts with React/TypeScript frontend
- Proven experience with cross-chain integrations, wallet connectivity, and decentralized storage (IPFS)
- Established development workflows with CI/CD, containerization, and automated testing


---

# Milestones & Deliverables

### Overview

- **Total Estimated Duration:** 12 weeks + 3 weeks buffer (≈4  months)
- **Full-Time Equivalent (FTE):** 1.9 FTE (average across project duration)
- **Total Costs:** $40,000 USD

## Milestone 1 — Core Smart Contracts & Infrastructure (4 Weeks)

- **Estimated Duration:** 4 weeks
- **FTE:** 1.5
- **Costs:** $10,000 USD
- **Total Hours:** ~205 hours (3 developers × ~17 hours/week each)


| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| **0a.** | License | Apache 2.0 |
| **0b.** | Documentation | We will provide both **inline documentation** of the code and a basic **tutorial** that explains how developers can set up the ink! development environment, deploy contracts to testnet, and interact with the project registry and round creation functionality. |
| **0c.** | Testing and Testing Guide | Core smart contract functions will be fully covered by comprehensive unit tests (>80% coverage) to ensure functionality and robustness. In the guide, we will describe how to run these tests using cargo-contract. |
| **0d.** | Docker | We will provide a Dockerfile that can be used to test all the smart contract functionality delivered with this milestone, including a local substrate node with contracts pallet. |
| 1. | ink! Smart Contract: Project Registry | We will create an ink! smart contract that manages project registration, GitHub verification status, and metadata storage (IPFS hashes). Functions include: `register_project()`, `verify_github()`, `update_metadata()`, `get_project_details()`. |
| 2. | ink! Smart Contract: Round Manager | We will create an ink! smart contract for funding round creation and management. Functions include: `create_round()`, `add_eligible_project()`, `set_badge_holders()`, `finalize_round()`. |
| 3. | ink! Smart Contract: Wallet Metadata | We will create an ink! smart contract to manage badge holder credentials and verification status. Functions include: `register_badge_holder()`, `verify_identity()`, `get_badge_holder_status()`. |
| 4. | Contract Integration Tests | We will deliver comprehensive integration tests demonstrating the interaction between Project Registry, Round Manager, and Wallet Metadata contracts. |
| 5. | Technical Specification Document | We will provide detailed specification of all contract interfaces, data structures, and integration patterns for future development phases. |

**Additional Success Criteria:**
- Specifications approved by project stakeholders
- Smart contracts deployed on testnet with verified functionality
- Automated test suites passed with >80% coverage
- Development environment reproducible and documented

---

## Milestone 2 — Frontend Platform & User Experience (4 Weeks)

- **Estimated Duration:** 4 weeks
- **FTE:** 1.75
- **Costs:** $11,000 USD
- **Total Hours:** ~240 hours (3 developers × ~20 hours/week each)

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| **0a.** | License | Apache 2.0 |
| **0b.** | Documentation | We will provide **inline documentation** of the code and a comprehensive **user guide** explaining how to connect wallets, register projects, create funding rounds, and participate as a badge holder. |
| **0c.** | Testing and Testing Guide | Frontend components and backend API endpoints will be covered by unit tests (Jest/React Testing Library) and integration tests. We will describe how to run these tests in the guide. |
| **0d.** | Docker | We will provide Docker Compose configuration that spins up the complete stack (frontend, backend, database, local blockchain node) for testing. |
| 1. | Backend API: User Management | We will implement a Node.js/PostgreSQL backend with REST API for user registration, wallet connection management, and project ownership tracking. Endpoints: `/api/auth/*`, `/api/users/*`. |
| 2. | Frontend: Authentication Flow | We will create React/Next.js components for wallet connection (Polkadot.js), optional email authentication, and session management with secure token handling. |
| 3. | Frontend: Badge Holder Voting Interface | We will implement the voting UI where badge holders can view eligible projects, allocate funds, and submit their votes on-chain. Includes real-time validation and transaction status tracking. |
| 4. | Frontend: Project Dashboard | We will create project owner dashboards showing registration status, round participation, funding received, and GitHub verification workflow. |
| 5. | Notification System | We will implement email and in-app notifications for round milestones (voting start, voting end, fund distribution) using a job queue system. |

**Additional Success Criteria:**
- Backend services integrated with Polkadot wallet infrastructure
- Authentication flows tested for security and usability
- Voting UI functional with live testnet data
- Positive feedback from internal testing team

---

## Milestone 3 — Advanced Features & Production Deployment (4 Weeks)

- **Estimated Duration:** 4 weeks
- **FTE:** 2.3
- **Costs:** $14,000 USD
- **Total Hours:** ~335 hours (4 developers with overlapping responsibilities, peak intensity phase)

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| **0a.** | License | Apache 2.0 |
| **0b.** | Documentation | We will provide complete **system documentation** including deployment guides, API reference, smart contract documentation, and operational runbooks for production deployment. |
| **0c.** | Testing and Testing Guide | End-to-end test suites covering complete user journeys (project registration → round creation → voting → fund distribution). Load testing results and performance benchmarks will be documented. |
| **0d.** | Docker | We will provide production-ready Docker Compose configuration with all services, monitoring, and logging infrastructure. |
| **0e.** | Article | We will publish an **article** on Medium/Polkadot Forum explaining: (1) How Eddink brings retroactive funding to ink! ecosystem, (2) Technical architecture and design decisions, (3) Tutorial for creating your first funding round, (4) Future roadmap and community governance plans. |
| 1. | Analytics Dashboard | We will implement comprehensive analytics views showing: round statistics, project funding history, badge holder participation rates, platform-wide metrics, and trend analysis. |
| 2. | Mainnet Deployment | We will deploy all smart contracts to Polkadot Asset Hub mainnet (or designated production testnet), with complete deployment documentation and contract addresses published. |
| 3. | Backend Infrastructure | We will set up production backend services with PostgreSQL database, IPFS integration for metadata storage, indexing services for blockchain data, and API rate limiting. |
| 4. | Monitoring & Observability | We will implement comprehensive monitoring using Prometheus/Grafana for system health, transaction tracking, error logging, and performance metrics. |
| 5. | Security Hardening | We will conduct security review, implement rate limiting, add input validation, secure API endpoints, and document security best practices for operators. |

**Additional Success Criteria:**
- Real-time dashboards operational with accurate data
- End-to-end tests passed with >70% coverage
- Smart contracts deployed and functional on production network
- Backend stable under simulated production load (100+ concurrent users)
- Platform ready for community beta testing

---

## Milestone 4 — Project Management & Contingency (Ongoing)

- **Estimated Duration:** Throughout project (12+3 weeks)
- **FTE:** 0.25
- **Costs:** $5,000 USD
- **Total Hours:** ~120 hours (10 hours/week average across 12 weeks)

**Scope:**
- Continuous project coordination, sprint planning, and stakeholder reporting
- Quality assurance reviews, code audits, and bug triage across all milestones
- Infrastructure costs (hosting, IPFS, testnet fees)
- Documentation maintenance and updates
- Buffer for minor unforeseen adjustments

**Success Criteria:**
- Timely delivery of all milestones
- Quality and performance standards consistently met
- Transparent progress tracking and effective communication maintained
- Weekly progress reports to stakeholders

---

## Team :busts_in_silhouette:

### Team members

- **Ahoura Azarbin** (Project Lead & Researcher)
- **Ali Pourgholami** (Lead Developer)
- **Aryan Kaushik** (Full-Stack Developer)
- **Mehrdad Mohammadzadeh** (System Architect)

### Contact

- **Contact Name:** Ahoura Azarbin
- **Contact Email:** ahouraazarbin@gmail.com
- **Website:** https://sustained-aachen.vercel.app/ (Prior work demonstration)

### Legal Structure

- **Registered Address:** Not applicable (Individual contributors)
- **Registered Legal Entity:** Not applicable (Individual contributors)

### Team's experience

Our team has successfully delivered multiple blockchain projects across different ecosystems:

**ink! & Polkadot Expertise:**
- Winner of Web3 Summit 2025 Quadratic Funding Bounty using ink! smart contracts
- Production-ready quadratic funding infrastructure with React/TypeScript frontend and Polkadot wallet integration

**Cross-Ecosystem Success:**
- Winner of Celestia's Mammothon (PrivaCT project)
- Blockscout Track Winner at ETHGlobal Prague (Prompt Genius)
- Active participation in Optimism's RPGF 3, providing firsthand retrofunding insights

**Production Development:**
- Ali: Delivered cross-chain swap infrastructure (Tron ↔ Ethereum), MLOps pipelines on AWS, and smart contract integrations
- Aryan: GDPR-compliant data anonymization at AXA Konzern AG, CI/CD pipeline migrations, THz-TDS image reconstruction
- Mehrdad: Concurrent software modeling, real-time systems design, network programming
- Ahoura: DevRel at growthepie, contract labeling standards, multi-chain analytics, published research on public goods funding

The team has proven ability to deliver production-ready blockchain applications on tight timelines while maintaining code quality and security standards.

### Team Code Repos

- https://github.com/prgprg/qf_front (Web3 Summit 2025 Winner - ink! Quadratic Funding)
- https://github.com/Aghostraa/PrivaCT (Celestia Mammothon Winner)
- https://github.com/Aghostraa/prompt_guesser (ETHGlobal Prague Blockscout Winner)

### Team Member GitHub Accounts

- https://github.com/aghostraa (Ahoura Azarbin)
- https://github.com/prgprg (Ali Pourgholami)
- https://github.com/Ark2588 (Aryan Kaushik)
- https://github.com/mmithridatess (Mehrdad Mohammadzadeh)

### Team LinkedIn Profiles

- https://www.linkedin.com/in/ahoura-azarbin/ (Ahoura Azarbin)

---

## **Ahoura Azarbin** - Project Lead & Researcher

Ahoura is a graduate of FH Aachen and former president of the Aachen Blockchain Club, as researcher and DevRel at growthepie, he focuses on labeling implementation and promoting Open Labels Initiative standard adoption for labeling smart contracts on the Ethereum Ecosystem. Together with the growthepie team, he has been involved in multiple grants and participated in multiple retroactive funding rounds notably the Optimism’s RPPG 3. He has also been a runner up in the Web3 Summit 2025 with his project Sustained wining the Quadratic Funding Bounty using Ink!. He has also been part of the winner team of the Celestia’s Mammothon with PrivaCT. He has also contributed academically to fill the gap of real world impact making and web3 tools through his research on the topic of quadratic funding and grass root sustainability intitiative.

### Technical Expertise

- Programming & Data (AI Assisted): TypeScript, Python, Solidity, SQL
- Frontend & UI/UX (AI Assisted): React, Next.js, Tailwind CSS, Vite
- Blockchain & Web3: EVM, web3.js, smart contract integration, contract labeling, multi-chain analytics
- Data & Integration: ETL workflows, database management, API integration
- Developer Relations: Documentation, technical content, community support, partnership enablement.

### Contact

- **Contact Name:** Ahoura Azarbin
- **Contact Email:** ahouraazarbin@gmail.com
- **GitHub:** @aghostraa

### References

- **Reference 1:** Sustained - Thesis on ResearchGate: https://www.researchgate.net/publication/395004196_Adaptive_Platform_for_Incentivizing_Pro-Environmental_Behavior_A_Framework_for_Impact_in_Aachen
    
    Demo: https://sustained-aachen.vercel.app/
    
- **Reference 2:** Celestia’s Mammothon Winner - Github: https://github.com/Aghostraa/PrivaCT
    
    Twitter: https://x.com/PrivaCT_dev
    
- **Reference 3:** Web3 Summit 2025 - Ink! Quadratic Funding Track Winner
    
    Github: https://github.com/prgprg/qf_front
    
- **Reference 4:** ETH Global Prague Submission - Blockscout Track Winner
    
    Github: https://github.com/Aghostraa/prompt_guesser Demo: https://prompt-guesser-nextjs.vercel.app/ ETH Global Showcase: https://ethglobal.com/showcase/prompt-genius-tv801
    

## Aryan Kaushik - Computer Engineer

Aryan is a Data Analyst at Wipro Technologies GmbH. He is currently pursuing his post graduation in Computer Science at the Karlsruhe Institute for Technology while specializing in the fields of Cryptography and Security and Human-Centered Machine Intelligence.  Aryan has been part of the PrivaCT team which was a winner team in Celestia’s Mammothon as well as the Prompt Genius team which won 2nd place on the ‘Best Blockscout SDK Integration’ bounty track at ETHGlobal Prague 2025. Academically, Aryan has also analyzed the application of recommender systems for vote delegation in DAOs as a potential method to combat voter apathy.

Aryan has also worked on projects like building a GDPR-compliant anonymization framework for customer data at AXA Konzern AG, enabling the creation of high quality development datasets from production data. He has also worked on the migration of a Jenkins based CI/CD pipeline to Tekton based CI/CD pipeline enabling a much better development workflow. As his bachelor thesis, he implemented sparse deconvolution for improving reconstruction quality of THz-TDS images which has application implications from security to cultural studies.

Technical skills:

- Programming skills: Python(numpy, pandas, tensorflow, pytorch, scikit-learn, scipy, streamlit), SQL, Javascript (react, node.js), Typescript, HTML, CSS, C++, Matlab, Git, Shell scripting, Containerization solutions (docker, kubernetes, openshift), Rust (AI-assisted), Solidity (AI-assisted).
- Blockchain tools: Scaffold-ETH 2, Snapshot, Tally, Dune Analytics, Hardhat

### Contact

- **Contact Name:** Aryan Kaushik
- **Contact Email:** aryankaushik2588@gmail.com
- **GitHub:** @Ark2588

### References

- **Reference 1:**  Celestia’s Mammothon Winner - PrivaCT: [https://github.com/Aghostraa/PrivaCT](https://github.com/ArK2588/PrivaCT)
    
    Twitter: https://x.com/PrivaCT_dev
    
- **Reference 2:** Blockscout Bounty Winner at ETHGlobal Prague  - Prompt Genuis
    
    Github: https://github.com/ArK2588/prompt_genius 
    EthGlobal Showcase: https://ethglobal.com/showcase/prompt-genius-tv801
    

## Mehrdad Mohammadzadeh - System Architect

Mehrdad is a post-graduate student of Computer Engineering M.Sc in RWTH Aachen. His projects and skillset is mostly revolves around concurrent software modeling and design. Mehrdad been a part of the winner team of PrivaCT in Celestia’s Mammothon and prompt-guesser in ETH Prague. 

### Technical Skills

concurrent rust, unsafe rust, real-time software design, network programming, low-Level programming, relational databases, scripting languages (bash, python), frontend (svelte, react), backend (rust, java)

### Contact

- **Contact Name:** Mehrdad Mohammadzadeh
- **Contact Email:** mmithridatess@gmail.com
- **GitHub:** @mmithridatess

### References

- **Reference 1:** Celestia’s Mammothon Winner Github: https://github.com/MmithridatesS/PrivaCT-service/
- **Reference 2:** ETH Global Prague Submission - Blockscout Track Winner
    
    Github: https://github.com/Aghostraa/prompt_guesser Demo: https://prompt-guesser-nextjs.vercel.app/ ETH Global Showcase: https://ethglobal.com/showcase/prompt-genius-tv801
    

## **Ali Pourgholami – Developer**

Ali is a multidisciplinary engineer focused on building reliable software systems and blockchain applications. He has delivered **production-ready quadratic funding** tooling using **ink! smart contracts** with a **React/TypeScript** frontend and Polkadot wallet integration, and implemented **cross-chain swap infrastructure** spanning **Tron ↔︎ Ethereum** with contract work and an accompanying interface integrated with **1inch Fusion+**. Beyond web3, Ali has shipped **MLOps and automation** at scale—developing ML pipelines, standing up cloud-native services on **AWS** (ECR, Lambda, SageMaker, DynamoDB, S3, CloudWatch), and hardening internal tooling and infrastructure with **Ansible** and Python. His background includes CI/CD, containerization, and HPC-adjacent workflows, enabling fast, reproducible delivery from prototype to production.

## **Technical Expertise**

• **Backend & DevOps:** Python, FastAPI, AWS (ECR, Lambda, SageMaker, DynamoDB, S3, CloudWatch), Docker, Kubernetes, Ansible/AWX, GitHub Actions

• **Blockchain & Web3:** ink! (Polkadot), Solidity, cross-chain integrations (Tron/EVM), smart contract development & integration, wallet flows, IPFS

• **Frontend:** React, TypeScript, Next.js

• **Data & Automation:** ETL pipelines, SQL, model packaging & deployment, monitoring/observability

## **Contact**

• **Name:** Ali Pourgholami

• **Email:** ali.pourgholami99@gmail.com

• **GitHub:** prgprg

• **Portfolio:** [Ali Pourgholami](https://prgprg.github.io/resume)

## References

- **Reference 1:** Web3 Summit 2025 - Ink! Quadratic Funding Track Winner
    
    Github: https://github.com/prgprg/qf_front

---

## Future Plans

Following the successful delivery of this foundational platform, we envision a phased expansion strategy:

**Phase 1 - Foundation (Months 1-6 post-launch):**
- Deploy on Polkadot Asset Hub mainnet and begin community beta testing
- Onboard 20+ initial funding rounds with diverse round creators
- Establish 200+ verified badge holders from Web3 Foundation grant recipients and active governance participants
- Distribute $100K+ through the platform, validating economic flows
- Maintain 99.5%+ uptime and zero critical security incidents

**Phase 2 - Community Integration (Months 7-18):**
- Integrate algorithmic evaluation tools to complement badge holder voting
- Deploy quadratic funding mechanisms for more equitable resource allocation
- Expand to 3+ additional parachains in the Polkadot ecosystem
- Achieve operational sustainability with >1.0 revenue-to-grant ratio
- Transition to community governance for platform parameters and algorithm selection

**Phase 3 - Scale & Sophistication (Months 19-36):**
- Launch full algorithmic evaluation marketplace where community votes on competing algorithms
- Implement cross-chain fund coordination via XCM for ecosystem-wide funding rounds
- Integrate advanced identity verification and enhanced sybil resistance mechanisms
- Support 1,000+ projects annually with sophisticated impact attribution
- Complete transition to community ownership and decentralized governance

**Long-Term Vision - "Sustained" Platform (36+ months):**
Our ultimate vision extends beyond digital public goods to support real-world impact initiatives. By proving the model works for ecosystem funding, we establish the credibility and technical foundation to expand into environmental restoration, social justice initiatives, and large-scale volunteer coordination. The platform will evolve to integrate real-world impact verification (IoT data, social impact metrics) while maintaining the transparent, decentralized coordination mechanisms built in this initial phase.

**Sustainability Commitment:**
- Open-source development model to enable community contributions and ecosystem adoption
- Revenue model (platform fees, premium features, treasury allocations) ensures long-term viability
- Active engagement with Polkadot governance to position Eddink as essential public goods infrastructure
- Continuous iteration based on community feedback and ecosystem needs

---

## Additional Information :heavy_plus_sign:

**How did you hear about the Bounty Program?**  
Through research into Polkadot ecosystem funding mechanisms and the ink!ubator program while investigating how to bring retroactive funding concepts to the Polkadot ecosystem.

**Work Already Completed:**
- Comprehensive research and analysis of Optimism's RetroFunding evolution (Seasons 4-8)
- Published academic research on quadratic funding and grassroots sustainability initiatives
- Delivered production-ready quadratic funding platform using ink! (Web3 Summit 2025 winner)
- Built technical prototypes demonstrating wallet integration, smart contract architecture, and voting mechanisms
- Established relationships with Polkadot community through conference participation and forum engagement

**Alignment with RFP Requirements:**  
This proposal directly addresses the specified RFP for "A retroactive funding platform, analogous to Gitcoin Grants" with the following features:
- **"Anyone can create a round":** Community-driven round creation with customizable parameters and transparent eligibility criteria
- **"Projects apply to rounds":** Streamlined application portal with GitHub verification and structured submission process
- **"Admins select eligible projects":** Admin curation system with transparent selection criteria and community oversight
- **"Badge holders choose fund distribution":** Sophisticated voting mechanisms for verified community members with on-chain transparency
- **"ink! smart contract structure":** Built natively on ink! v6 with full Polkadot ecosystem integration

**Additional Context:**
- This project represents months of research into retrofunding mechanisms and public goods coordination
- Team has proven track record delivering blockchain projects on tight timelines
- Platform designed with clear expansion paths while maintaining focus on deliverable scope
- Commitment to open-source development (Apache 2.0 license) and comprehensive documentation
- Strong emphasis on security, testing, and production readiness from day one

**No Other Financial Contributors:**  
This project is currently self-funded through team members' time investment. No other teams or organizations have contributed financially to date.
