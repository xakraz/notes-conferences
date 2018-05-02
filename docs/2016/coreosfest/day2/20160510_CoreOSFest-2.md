20160510_CoreOSFest-2
---------------------

<!-- MarkdownTOC -->

- [JWTProxy intro](#jwtproxy-intro)
- [v1](#v1)
  - [Authentication mechanism](#authentication-mechanism)
  - [Issues Feedbacks](#issues-feedbacks)
- [v2](#v2)
  - [JWT](#jwt)
  - [Demo](#demo)
- [RSA notes](#rsa-notes)
- [Future](#future)

<!-- /MarkdownTOC -->


Secure auth between services


# JWTProxy intro

Motivations:
* Many services respect HTTP_PROXY env variables
* Proxy allow to be language agnostics / app agnostic
* Inspired by Oauth_proxy service

Downside
- 1 Extra network Hop



# v1

## Authentication mechanism

TLS Clients Certs (we considered)
* Already used between Quay / clair
* BUT PKI integration in enterprise in complicated
* BUT When LB / other teams dependency
=> DROPPED

HMAC
* Hash of Message + Secret_key
* Virtues
  - No secrets needed in the requests
  - Fast
  - Request is self-signed


## Issues Feedbacks

* Request signature
-> Headers are also signed !
-> BUT Extra headers from intern LB



# v2

## JWT

Virtues
* Secret is NERVER transmit
* Signed
* Resistant to replay attacks (Annonce mechanism)
* Can be transmited in the clear
* Request optionaly signed

+ SSL Everywhere


## Demo

* Use `request-bin` that is opensource and can be self hosted to debug HTTP request
* Start JWTProxy service
  - Generate a RSA key pair locally
  - Submit to a PKI for approval + Wait
* ...



# RSA notes

* Key rotations easy



# Future

* Performance enhancement for RSA keypair generation
* Integration for Auto-validation of keys
* Caching keys if PKI server is unavailable
* "Nonce" protection



