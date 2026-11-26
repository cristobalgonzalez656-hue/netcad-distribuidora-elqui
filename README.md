# 🌐 NetCAD — Diseño, Trazado y Cubicación de Red UTP (Distribuidora Elqui SpA)

[![Cloudflare Pages](https://img.shields.io/badge/Cloudflare%20Pages-En%20Vivo-F38020?style=for-the-badge&logo=cloudflare&logoColor=white)](https://netcad-distribuidora-elqui.pages.dev)
[![Normativa TIA](https://img.shields.io/badge/Normativa-ANSI%2FTIA--568.2--D%20%7C%20569%20%7C%20606-0052CC?style=for-the-badge)](#parámetros-técnicos-del-proyecto)
[![Enlaces](https://img.shields.io/badge/Enlaces%20Permanentes-72%2F72%20%E2%89%A4%2090m-10B981?style=for-the-badge)](#arquitectura-y-topología-de-red)
[![Presupuesto](https://img.shields.io/badge/Presupuesto%20c%2FIVA-%2412.388.054%20CLP-1E293B?style=for-the-badge)](#cubicación-y-presupuesto-resumen)

> **Plataforma web de ingeniería** desarrollada para la asignatura **Infraestructura de Redes (TCB304)** — **INACAP Sede La Serena**. Resuelve integralmente el diseño de cableado estructurado Categoría 6, cobertura inalámbrica Wi-Fi 6, videovigilancia IP, elevación de racks, cubicación, presupuesto en CLP y planificación de obra.

---

### 🔗 Enlaces Oficiales de Entrega
* **Aplicación Web Interactiva (Cloudflare Pages):** https://netcad-distribuidora-elqui.pages.dev
* **Repositorio de Código (GitHub):** https://github.com/cristobalgonzalez656-hue/netcad-distribuidora-elqui
* **Autor:** Cristóbal Plaza González

---

## 📋 Parámetros Técnicos del Proyecto

| Parámetro de Ingeniería | Especificación / Valor del Diseño | Norma / Criterio Aplicado |
| :--- | :--- | :--- |
| **Cliente e Instalación** | Distribuidora Elqui SpA — Galpón Industrial, La Serena | Planta 1° Piso (`64,00 m × 30,00 m`) + Patio (`12,00 m`) |
| **Topología de Red** | Estrella jerárquica de 2 niveles (`R1 MDF` + `R2 IDF`) | ANSI/TIA-568.2-D (Enlaces permanentes ≤ 90 m) |
| **Enlace Permanente Máximo** | **54,2 m** (`PAT-CAM02` hacia `R2 IDF`) | Resuelve exceso de 118,2 m sin rack secundario |
| **Total Puntos de Red** | **72 enlaces activos** + **2 enlaces troncales** (`38,0 m`) | 62 datos Gigabit + 6 APs Wi-Fi 6 + 4 Cámaras IP PoE+ |
| **Cableado Interior** | U/UTP Categoría 6, cubierta **LSZH** (`10 cajas` de 305 m) | 2.840,5 m c/merma (`3,0 m` rack + `0,30 m` salida + `10%`) |
| **Cableado Exterior** | U/UTP Categoría 6, cubierta **PE** (`1 bobina` de 305 m) | 149,5 m c/merma exclusivo para Patio de Carga |
| **Alimentación PoE** | Estándar **IEEE 802.3at (PoE+)** | 6 Access Points (interior/IP67) + 4 Cámaras IP 4MP |
| **Gabinetes / Racks 19"** | **R1 MDF** (Piso 32U) y **R2 IDF** (Mural 12U a 3,0 m) | Reserva ≥ 30% en unidades `U`, Patch Panels y Switches |
| **Canalización** | Bandeja cielo falso (`2,70 m`) / Bandeja bodega (`6,00 m`) | Bajadas en canaleta PVC (`0,40 m`) y conduit EMT |
| **Etiquetado** | Nomenclatura estructurada en ambos extremos | Norma **ANSI/TIA-606** (`[Recinto]-[N°][Boca]`) |
| **Plazo y Cuadrilla** | **10 días hábiles** (jornadas de 9 h) | 2 Técnicos + 1 Supervisor (100% enlaces certificados) |
| **Inversión Total Obra** | **$12.388.054 CLP** (IVA 19% incluido) | Materiales, ferretería, mano de obra y arriendo equipos |

---

## 🏗️ Arquitectura y Topología de Red

```text
[Proveedor ISP / ONT]
        │
[R1-RTR1 Firewall 1U]
        │
┌───────┴──────────────────────────────────────────────────────────┐
│  R1 — RACK PRINCIPAL MDF (Gabinete Piso 32U · Sala Telecom.)     │
│  • R1-PP1 a PP4 (4×24p Cat 6) + 5 Organizadores Horizontales 1U  │
│  • R1-SW1 a SW3 (3×24p Gigabit) + R1-SW4 (24p PoE+ 802.3at)      │
│  • R1-NVR1 (Grabador IP 4TB) + R1-PDU1 + R1-UPS1 Online 2000VA   │
└───────┬──────────────────────────────────┬───────────────────────┘
        │ 65 Enlaces Oficinas              │ 2× Trunk Cat 6 LSZH (38,0 m)
        ▼ (≤ 49,0 m)                       ▼
[Oficina Abierta, Contab.,         ┌───────────────────────────────┐
 RR.HH., Recepción, Reuniones,     │ R2 — RACK SECUNDARIO IDF      │
 Gerencia y Oficina Bodega]        │ (Gabinete Mural 12U · Bodega) │
                                   │ • R2-PP1 (24p) + R2-ORG1 (1U) │
                                   │ • R2-SW1 (24p PoE+ 802.3at)   │
                                   │ • R2-PDU1 (1U) + R2-UPS1 (2U) │
                                   └───────┬───────────────────────┘
                                           │ 7 Enlaces PoE+ (≤ 54,2 m)
                                           ▼
                                   [Bodega 6,0m: 2 APs + 2 Cámaras]
                                   [Patio Exterior PE: 1 AP + 2 Cám.]
