# caleta-app# 🌊 Caleta App — Caleta Protocol

> Bóveda DeFi de generación de rendimiento y tokenización de liquidez desplegada en **Tuxachain / Aurora Engine**.

[![Network: Tuxachain](https://img.shields.io/badge/Network-Tuxachain-blue.svg)](https://tuxachain.net)
[![EVM Version: Paris](https://img.shields.io/badge/EVM-Paris-orange.svg)]()
[![Solidity: 0.8.20](https://img.shields.io/badge/Solidity-0.8.20-lightgrey.svg)]()
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

---

## 📌 Descripción General

**Caleta Protocol** es un ecosistema descentralizado de bóvedas de rendimiento que permite a los usuarios depositar sus activos (como **WNEAR**), acumular dividendos pasivos distribuidos en **USDT**, y optar por liquidez inmediata a través de una arquitectura de tokens espejo y wrappers ERC-20.

El protocolo garantiza la paridad financiera mediante contabilidad de doble partida on-chain y separación estricta entre la prueba de participación soulbound (**Morocota / MORO**) y el activo líquido transferible (**Cobres**).

---

## 🪙 Arquitectura de Tokens y Flujo Económico

El ciclo de vida del capital en Caleta Protocol consta de 3 capas principales:

```text
               ┌─────────────────────────────────────────┐
               │    Depósito de Activo Base (WNEAR)      │
               └────────────────────┬────────────────────┘
                                    │
                                    ▼
               ┌─────────────────────────────────────────┐
               │    Emisión de Morocota (MORO) 1:1       │
               │   (Token Soulbound / Recibo Bóveda)     │
               └───────────┬─────────────────▲───────────┘
                           │                 │
              Wrap (Mint)  │                 │ Unwrap (Burn)
                           ▼                 │
               ┌─────────────────────────────────────────┐
               │         Token COBRES (ERC-20)           │
               │   (Token Líquido / Transferible / DEX)  │
               └─────────────────────────────────────────┘
