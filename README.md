# Taller 1
##### https://sites.google.com/site/mariacecipardo/bioestadistica-biol110
## BIOL1100/Sección 1
## Integrantes:
### Rodrigo Fernández/(rodrigojeromefs@gmail.com)
### Nicolás Gallardo/(nigallardorubio@gmail.com)
### Alejandro Lara/(a.laraparra1@gmail.com)
### Jonathan Oñate/(j.arieloate@gmail.com)
### 1. Determine en R cuáles de las siguientes especies de anfibios son propias de la zona norte, de la zona sur y cuáles especies son compartidas entre ambas regiones, es decir, las especies que están presentes en la zona norte y en la zona sur. Responda en base a la teoría de conjuntos. Realice un diagrama de Venn para representar el problema.
##### library(VennDiagram)
#### Zona_Norte_de_Chile=ZN; Zona_Centro_Sur_de_Chile=ZCS
##### ZN<-c("Telmatobius_marmoratus","Telmatobius_pefauri","Telmatobius_philippii","Telmatobius_halli","Rhinella_spinulosa","Rhinella_atacamensis","Pleurodema_marmorata","Pleurodema_thaul")
##### ZN
##### ZCS<-c("Alsodes_nodosus","Alsodes_montanus","Eupsophus_vertebralis","Calyptocephalella_gayi","Rhinella_arunco","Rhinella_spinulosa","Rhinella_atacamensis","Xenopus_laevis","Pleurodema_thaul","Pleurodema_bufonina")
##### ZCS
##### intersect(ZN,ZCS)
##### draw.pairwise.venn(area1=8,area2=10,cross.area=3,category=c("ZN","ZCS"))
### 2. ¿Cuántas permutaciones de 3 nucleótidos sin repetir podemos hacer con las bases A, C, T y G? Obtenga todas las permutaciones posibles en R. Demuestre este resultado mediante la fórmula de permutaciones.
##### library(gtools)
##### NCs<-c("A","C","T","G")
##### NCs
##### permutations(4,3,NCs,repeats.allowed=F)
#### R: Son 24 permutaciones que se pueden hacer con 3 de los 4 nucleótidos, sin reemplazo.
#### Demostracción:
##### factorial(4)/factorial(4-3)
### 3. La probabilidad de obtener la palabra CASA con las letras “C”, “A”, “S” y “A” es de 0.1. Obtenga 150 muestras aleatorias (al azar) de 4 elementos con esas letras y determine si se cumple esa predicción.
##### Hs<-c("C","A","S","A")
##### Hs
##### replicate(150,sample(Hs,size=4,replace=F))
##### 19/150
#### R: La probabilidad de obtener la palabra CASA dentro de las 150 muestras fue de 0.1266667 (aprox. 0.1), por lo tanto, se cumple la predicción.
### 4. Tire una moneda virtual 40 veces con el comando sample() y determine si le salen 20 caras y 20 sellos (para eso, incluya replace = TRUE en la función para obtener un muestreo con remplazo). Al comparar los resultados de los intentos ¿cuántas caras y sellos se obtienen? ¿El resultado corresponde al esperado (20 caras y 20 sellos)?
##### MV<-c("Cara","Sello")
##### MV
##### replicate(40,sample(MV,size=1,replace=T))
#### R: se obtuvo 23 caras y 17 sellos, lo que se traduce en cercano, pero no exacto a lo postulado en el encabezado.
### 5. Determine cuántas permutaciones de 4 elementos con y sin repetición se pueden formar con las letras “P”, “E”, “R” y “O”. Use el comando permutations() con los argumentos repeats.allowed = TRUE (con repetición) ó repeats.allowed = FALSE (sin repetición). Además, demuestre este resultado matemáticamente.
##### E<-c("P","E","R","O")
##### E
##### permutations(4,4,E,repeats.allowed=T)
#### Demostración:
##### 4^4
##### permutations(4,4,E,repeats.allowed=F)
#### Demostración:
##### factorial(4)
#### R: Se pueden formar 256 permutaciones con repetición y 24 sin repetición.
