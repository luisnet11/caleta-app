# 🪙 Caleta App — Caleta Protocol

> Bóveda DeFi de generación de rendimientos sostenibles basada en la delegación de activos en **NEAR Protocol** y despliegue en **Tuxachain / Aurora Engine**, distribuyendo recompensas en **USDT**.

[![Network: Tuxachain](https://img.shields.io/badge/Network-Tuxachain-blue.svg)](https://tuxachain.net)
[![EVM Version: Paris](https://img.shields.io/badge/EVM-Paris-orange.svg)]()
[![Solidity: 0.8.20](https://img.shields.io/badge/Solidity-0.8.20-lightgrey.svg)]()
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

---

## 📌 Descripción General

**Caleta Protocol** es un protocolo descentralizado diseñado para optimizar el rendimiento de activos depositados (como **WNEAR**). El protocolo toma los fondos depositados, los gestiona mediante una estrategia de delegación a nodos validadores en la red de **NEAR Protocol**, y genera rendimientos pasivos que se pagan directamente en la stablecoin **USDT**.

El ecosistema combina la seguridad de la contabilidad de doble partida on-chain con un mecanismo de retribución directa al usuario y sostenibilidad a largo plazo mediante la reinversión de ganancias en otros protocolos DeFi.

---

## ⚙️ Funcionamiento del Protocolo y Flujo Financiero

### 1. División del Depósito Principal
Cada vez que un usuario realiza un depósito en la bóveda (ej. en **WNEAR**), el contrato inteligente divide automáticamente los fondos en tres flujos clave para garantizar operabilidad y seguridad:

* **90% $\rightarrow$ Billetera de Estrategia e Inversión (`strategyWallet`):** Se destina a la delegación directa en un nodo validador de la red de **NEAR Protocol** para la generación activa de staking rewards.
* **5% $\rightarrow$ Billetera de Respaldo (`backupWallet`):** Fondo de reserva externo y contingencia operativa frente a fluctuaciones de mercado.
* **~5% $\rightarrow$ Liquidez Local del Contrato:** Permanece retenido directamente en el contrato inteligente para mantener liquidez inmediata y cubrir imprevistos.

```text
                                  ┌───────────────────────────┐
                                  │   Depósito Usuario (WNEAR)│
                                  └─────────────┬─────────────┘
                                                │
                                                ▼
                        ┌───────────────────────────────────────────────┐
                        │        Contrato Inteligente Bóveda            │
                        └───────┬───────────────┬───────────────┬───────┘
                                │               │               │
                      90%       │            5% │               │ ~5%
                                ▼               ▼               ▼
                      ┌──────────────────┐ ┌──────────┐ ┌───────────────┐
                      │ Strategy Wallet  │ │  Backup  │ │ Liquidez Local│
                      │ (Nodo Validador) │ │ Wallet   │ │ (En Contrato) │
                      └─────────┬────────┘ └──────────┘ └───────────────┘
                                │
                                ▼
                      ┌──────────────────┐
                      │ Rendimientos NEAR│
                      └──────────────────┘
