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
* **Autor:** Cristóbal González Guerrero

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
| **Alimentación PoE** | Estándar **IEEE 802.3at (PoE
