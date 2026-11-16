<div align="center">

# Mayur Kumawat

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=500&size=22&duration=3200&pause=900&color=00ADD8&center=true&vCenter=true&width=720&height=36&lines=Senior+Backend+Engineer;Go+%C2%B7+Microservices+%C2%B7+Distributed+Systems;Monolith+%E2%86%92+microservices+migrations;Database+scalability+%26+caching" alt="Senior Backend Engineer · Go · Microservices · Distributed Systems" />

<br />

<a href="mailto:mayurkumawat012@gmail.com"><img src="https://img.shields.io/badge/Email-mayurkumawat012%40gmail.com-D14836?style=flat-square&logo=gmail&logoColor=white" alt="Email" /></a>
&nbsp;
<img src="https://img.shields.io/badge/Location-Udaipur%2C%20India-2ea44f?style=flat-square&logo=googlemaps&logoColor=white" alt="Udaipur, India" />
&nbsp;
<img src="https://img.shields.io/badge/Experience-7%2B%20years-00ADD8?style=flat-square&logo=clockify&logoColor=white" alt="7+ years of experience" />
&nbsp;
<a href="https://open.spotify.com/artist/66lDCwW30gGctutEDqD7mn"><img src="https://img.shields.io/badge/Spotify-Mayur%20Kumawat-1DB954?style=flat-square&logo=spotify&logoColor=white" alt="Spotify" /></a>

<br /><br />

<img src="https://img.shields.io/badge/840%2B-Jira%20issues-0052CC?style=flat-square&logo=jira&logoColor=white" alt="840+ Jira issues delivered" />
&nbsp;
<img src="https://img.shields.io/badge/130%2B-bugs%20resolved-CB2431?style=flat-square" alt="130+ bugs resolved" />
&nbsp;
<img src="https://img.shields.io/badge/3-engineering%20squads-6f42c1?style=flat-square" alt="3 engineering squads" />

</div>

---

### About me

I build and operate backend systems in **Go**. For the past four years I have worked on **SkoolNet**, the preschool management platform of **NTUC First Campus**, moving a Go monolith to microservices and keeping the data layer fast and reliable while that happens.

Before that I built geospatial APIs at **Kawa Space**, enterprise applications at **Cognizant**, and conversational AI backends at **Botosynthesis**.

The problems I enjoy most are the unglamorous ones: connection pools that starve under load, caches that go stale, and batch jobs that must not send the same email twice.

---

### Tech stack

| | |
| :--- | :--- |
| **Languages** | ![Go](https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white) ![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black) ![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white) ![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) |
| **Data & caching** | ![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white) ![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white) ![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white) ![BigQuery](https://img.shields.io/badge/BigQuery-669DF6?style=flat-square&logo=googlebigquery&logoColor=white) |
| **Messaging & APIs** | ![Pub/Sub](https://img.shields.io/badge/Cloud%20Pub%2FSub-4285F4?style=flat-square&logo=googlecloud&logoColor=white) ![Kafka](https://img.shields.io/badge/Apache%20Kafka-000000?style=flat-square&logo=apachekafka&logoColor=white&labelColor=4B4B4B) ![GraphQL](https://img.shields.io/badge/GraphQL-E10098?style=flat-square&logo=graphql&logoColor=white) ![REST](https://img.shields.io/badge/REST%20APIs-02569B?style=flat-square&logo=swagger&logoColor=white) |
| **Cloud & delivery** | ![GCP](https://img.shields.io/badge/Google%20Cloud-4285F4?style=flat-square&logo=googlecloud&logoColor=white) ![AWS](https://img.shields.io/badge/AWS%20S3%20%2B%20CloudFront-FF9900?style=flat-square&logo=amazonaws&logoColor=white) ![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white) ![Bitbucket](https://img.shields.io/badge/Bitbucket%20Pipelines-0052CC?style=flat-square&logo=bitbucket&logoColor=white) ![SonarCloud](https://img.shields.io/badge/SonarCloud-F3702A?style=flat-square&logo=sonarcloud&logoColor=white) |

---

### Selected work

<details open>
<summary><b>Carving a survey service out of a monolith</b> · led end to end</summary>
<br />

I led the design and delivery of a parent satisfaction survey microservice, from first design through production cutover. Survey generation, distribution, response capture and reporting moved out of the monolith into a standalone service with its own database, Kubernetes deployments and a CI/CD pipeline with quality gates.

| Problem | What I did |
| --- | --- |
| Survey links carried internal identifiers in the URL, open to enumeration and tampering | Replaced them with opaque UUID tokens resolved on the server, added short-lived JWT authentication to every endpoint, and migrated links already in flight |
| A failed batch job meant duplicate emails or half-finished state | Added MongoDB-based checkpoints so jobs resume where they stopped, and batched dispatch centre by centre to stay within mail-server limits |
| Heavy cron runs exhausted database connections | Pooled external connections across multiple MySQL read replicas |

The service then went through a third-party security audit.

</details>

<details>
<summary><b>Attendance migration and cross-service consistency</b></summary>
<br />

- Migrated child check-in/check-out out of the monolith into dedicated microservices, with event handlers, API client layers and rate-limiting middleware.
- Designed and implemented distributed transactions across the onboarding and finance services, so registration and student-status updates stay consistent when a step fails.
- Analysed and carried out the retirement of Kafka in favour of Google Cloud Pub/Sub and direct service events, simplifying the messaging stack.

</details>

<details>
<summary><b>Database scalability</b></summary>
<br />

- Routed hot read queries and high-traffic APIs to read replicas to protect the primary database, and characterised replica routing behaviour ahead of weighted traffic distribution.
- Built stored-procedure archival workflows for microservice data, including notification cleanup and audit-table maintenance, to keep table growth under control.
- Diagnosed slow queries and introduced distributed tracing in APIs to find where time was going.

</details>

<details>
<summary><b>Caching</b></summary>
<br />

- Designed a Pub/Sub-based cache invalidation framework across facade services to prevent stale reads after updates.
- Moved Redis key lookups from blocking key scans to cursor-based <code>SCAN</code>.

</details>

<details>
<summary><b>Security and reliability</b></summary>
<br />

- Moved public file uploads (portfolios, activity media, profile images) to private S3 buckets served through CloudFront presigned URLs, across GraphQL and REST resolvers.
- Remediated penetration-test findings around authorization checks, access-control validation and error-message leakage.
- Replaced national ID numbers with system-generated guardian identifiers across parent apps and centre kiosks, including credential synchronisation and race-condition handling during concurrent record creation.
- Set up MongoDB clusters for disaster recovery, migrated secrets to Google Secret Manager, parallelised deployment pipelines, and reworked alert routing so critical production issues are not lost in noise.

</details>

---

### Career

| Period | Role | What I worked on |
| --- | --- | --- |
| Oct 2022 – Present | **Senior Software Developer (Consultant)**, NTUC First Campus | Go microservices for SkoolNet across three squads: attendance, onboarding, finance, identity, reporting and platform reliability |
| Oct 2021 – Oct 2022 | **SDE-2**, Kawa Space | Go services and APIs for a satellite data analytics platform; farm report system; ML pipeline input changes; Airflow to Cloud Run migration |
| Jan 2021 – Oct 2021 | **Full-Stack Engineer**, Cognizant | Enterprise application modules with Spring Boot and Angular on AWS |
| Oct 2019 – Jan 2021 | **Full-Stack Engineer**, Botosynthesis | Node.js backend for multi-language chatbots; Google NLP and speech API integrations; voice bot for interview preparation |

**Education:** B.Tech, Techno India NJR Institute of Technology (Rajasthan Technical University), 2016 – 2020

---

### Beyond the code

When I am not working on backend systems, I make music. I sing, play guitar and release my own songs under my name. I also play table tennis.

<p align="center">
  <a href="https://open.spotify.com/artist/66lDCwW30gGctutEDqD7mn"><img src="https://img.shields.io/badge/Listen%20on%20Spotify-1DB954?style=for-the-badge&logo=spotify&logoColor=white" alt="Listen on Spotify" /></a>
</p>

---

<p align="center">
  <a href="mailto:mayurkumawat012@gmail.com"><img src="https://img.shields.io/badge/Get%20in%20touch-mayurkumawat012%40gmail.com-00ADD8?style=for-the-badge&logo=gmail&logoColor=white" alt="Email Mayur" /></a>
</p>
