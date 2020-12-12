---
title: "Guide to use Haver Analytics"
author: "Victor Cuspinera"
collection: projects
type: "Guide"
permalink: /projects/2020/haver-guide
venue: "MDS-UBC GitHub"
date: 2020-12-11
location: "Mexico City, Mexico"
tags:
  - R
  - Pyhon
  - Haver Analytics
  - Banxico
---

**Haver Analytics** is a company that collects Economic, Financial and Monetary **time series** in real time from international and official primary sources as Central Banks and Governments. Some institutions, as Banco de Mexico, have a subscription to consult the Haver Analytic's databases. The aim of this project is to share a Guide to use Haver Analytics, as **R bookdown**, which initial objective is helping my colleagues from Banco de Mexico to retrieve information from these databases using R, Python and tools developed by Haver.  
$\bigstar$ *[Click here](https://bookdown.org/vcuspinera/Guide_Haver_Analytics/) to see the Guide to use Haver Analytics.*  

*Author: Victor Cuspinera ([vcuspinera](https://github.com/vcuspinera))*  


```diff
# ⚠️ The views and conclusions presented in this project are exclusively #
#     the responsibility of the author and do not necessarily reflect    #
#     those of Banco de Mexico.                                          #
```

## Guía para usar Haver Analytics
*__Guide to use Haver Analytics__*  
*⚠️ Warning: the content of this document is in Spanish.*

## Resumen
Como se mencionó en el *abstract*, [Haver Analytics](http://www.haver.com) es una empresa que se encarga de recopilar en tiempo real, con un rezago de aproximadamente 5 minutos, bases de datos con información económica, financiera y monetaria, a nivel global de distintas fuentes primarias oficiales como bancos centrales y gobiernos, o instituciones con gran reputación como el Fondo Monetario Internacional (IMF), y Universidades como Oxford y Johns Hopkins.  Algunas instituciones, como el Banco de México, tienen contratada una subscripción a algunas de las bases de datos de esta empresa.  

Esta guía fue desarrollada para ayudar a mis compañeros del Banco de México a consultar estas bases de datos usando R, Python y otras herramientas desarrolladas por Haver.  

[Click aquí](https://bookdown.org/vcuspinera/Guide_Haver_Analytics/) para acceder al libro electrónico con la Guía para usar Haver Analytics.

## Índice

1. [Introducción](https://bookdown.org/vcuspinera/Guide_Haver_Analytics/)  
    1.1. [Salvedad de uso](https://bookdown.org/vcuspinera/Guide_Haver_Analytics/#salvedad-de-uso)  
2. [Prerequisitos](https://bookdown.org/vcuspinera/Guide_Haver_Analytics/prereq.html)  
    2.1. [Instalación del software](https://bookdown.org/vcuspinera/Guide_Haver_Analytics/prereq.html#instalación-del-software)
3. [Acceso](https://bookdown.org/vcuspinera/Guide_Haver_Analytics/acceso.html)
    3.1. [Aplicación DLX](https://bookdown.org/vcuspinera/Guide_Haver_Analytics/acceso.html#aplicación-dlx)  
    3.2. [Add-in para Excel](https://bookdown.org/vcuspinera/Guide_Haver_Analytics/acceso.html#add-in-para-excel)  
    3.3. [Consulta con R](https://bookdown.org/vcuspinera/Guide_Haver_Analytics/acceso.html#consulta-con-r)  
    3.4. [Consulta con Python](https://bookdown.org/vcuspinera/Guide_Haver_Analytics/acceso.html#consulta-con-python)  
4. [Series](https://bookdown.org/vcuspinera/Guide_Haver_Analytics/series.html)
    4.1. [Bases de datos](https://bookdown.org/vcuspinera/Guide_Haver_Analytics/series.html#bases-de-datos)  
    4.2. [Código de Series](https://bookdown.org/vcuspinera/Guide_Haver_Analytics/series.html#código-de-series)  
5. [Contacto](https://bookdown.org/vcuspinera/Guide_Haver_Analytics/contacto.html)  
6. [Referencias](https://bookdown.org/vcuspinera/Guide_Haver_Analytics/referencias.html)  

## Repositorio en Github
Además, puedes acceder al repositorio de Github de este libro electrónico en *R bookdown* en el [siguiente link](https://github.com/vcuspinera/Guide_Haver_Analytics).  
