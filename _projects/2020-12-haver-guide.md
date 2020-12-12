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

**Haver Analytics** is a company that collects Economic, Financial and Monetary **time series** in real time from international and official primary sources as Central Banks and Governments. Some institutions, as Banco de Mexico, have a subscription to consult the Haver Analytic's databases. The aim of this project is to share a Guide to use Haver Analytics, as **R bookdown**, which initial objective is helping my collegues from Banco de Mexico to retrieve information from these databases using R, Python and tools developed by Haver.  
$\bigstar$ *[Click here](https://bookdown.org/vcuspinera/Guide_Haver_Analytics/) to see the Guide to use Haver Analytics.*
<center>⚠ Warning: the content of this Guide is in Spanish</center>

*Author: Victor Cuspinera ([vcuspinera](https://github.com/vcuspinera))*  


```diff
# ⚠️ The views and conclusions presented in this project are exclusively #
#     the responsibility of the author and do not necessarily reflect    #
#     those of Banco de Mexico.                                          #
```


Haver Analytics es una empresa que se encarga de recopilar casi en tiempo real (con lag de 5 minutos) bases de datos con información económica, financiera y monetaria, a nivel global de distintas fuentes primarias oficiales como bancos centrales y gobiernos, o instituciones con gran reputación (IMF, Oxford, Johns Hopkins, etc.).   El Banco de México tiene contratada una subscripción a algunas de las bases de datos de esta empresa, por lo que cualquier trabajador del banco puede solicitar el acceso a esta información sin incurrir en costo adicional alguno.


La guía que les comparto está enfocada a la Oficina de Estadística, pero podría ser útil para las distintas oficinas de la Subgerencia y tal vez Gerencia.

Para poder publicar la guía como libro electrónico (R book) tuve que hacer un repositorio público en github (lo pueden ver aquí), por lo que no incluí las credenciales para acceder material de consulta como las guías completas en R y Python; sin embargo, en el siguiente cuadro encontrarán esta información por si la llegan a necesitar:
