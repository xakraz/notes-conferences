20160615_3_Secrets-WithContainers
----------------------------------

<!-- MarkdownTOC -->

- [Agenda](#agenda)
- [Terms](#terms)
- [Containers world](#containers-world)
- [Secrets management tools](#secrets-management-tools)
- [SI for containers](#si-for-containers)

<!-- /MarkdownTOC -->


# Agenda

What it is about:
* Paradigm + Pattern
* Workflow

What it is not:
* A TRUTH guide
* A deep dive



# Terms

Security:
- Risk management
- Accepting some
- Guarding

Risk:
- Increase with system complexity

Secret:
- Elevate risk if exposed
- Threat

Diff secrets / identifiers
- Identifier should not be discoled but are not secrets

Trust:
- Entity
- Circle of Trust
- Chain of Trust

Circle of Trust
- Storage of secrets

Chain of trust
- Set of linkgs where the secret travels through
- A link is an interception point



# Containers world

Classic actors:
- Scheduler
- Scheduler Agent
- Container
- Secret Management

=> Lots of moving part


Problems / Criteria
1. Secrets protection
2. Secrets distribution
3. Complexity
4. Access detection
5. Break-glass procedure (If compromised)
  - Revoke everything - Stop access to secret
  - Audit and check your trust chain
  - Rotate new keys



# Secrets management tools

Many exists
BUT, not made for dynamic environment



# SI for containers

Vault
- Primitives for dynamic cred mgnt


Vault + Scheduluer = <3
- Scheduler are source of TRUTH


Preconditions
- Unlimited / Limited use-count
- Limited TTL (Renewable)
- Access / Actions Policies
- Scope


Example:

```
Scheduler
- Create a new Instance
- Sunmit to Agent

Scheduler agent
- Has Token
  + Scope: App_token_create
- Contact Vault
- Get a TMP token of the container
  + Use count 1
  + TTL 30s
- Provide the Token to the container

Container
- Contact Vault with temp token
  + Use count => 0
- Gets a new dedicated token
  + Use count: unlimitted
  + TTL 1h
- Use this token to get Creds for every 3rd service it needs to connect at starting
  => TTL 1h
```

=> We got:
- Limited time for secrets
- Limited access
- Limited usage
















