---
id: arquitetura-da-aplicacao
title: Arquitetura da Aplicação
sidebar_label: Aplicação
sidebar_position: 2
---

# Arquitetura da Aplicação

A WeCare opera em um modelo SaaS (Software as a Service), permitindo que múltiplos clientes utilizem a plataforma de forma segura e isolada.

## Modelo da Aplicação

A aplicação é estruturada como um sistema web centralizado, composto por:

* interface web para usuários
* API REST para integrações externas
* serviços internos responsáveis por processamento e regras de negócio

## Comunicação

A comunicação entre clientes e a plataforma ocorre via HTTPS, garantindo criptografia em trânsito.

As integrações externas são realizadas por meio de API REST autenticada.

## Autenticação

A autenticação das APIs é baseada em tokens (JWT), garantindo segurança e rastreabilidade nas integrações.

## Banco de Dados

A aplicação utiliza banco de dados relacional, com controle de acesso e segregação lógica entre clientes.

## Segurança da Aplicação

A aplicação segue boas práticas de desenvolvimento seguro, incluindo validação de entradas, controle de acesso e proteção contra vulnerabilidades conhecidas.
