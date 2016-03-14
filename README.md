# 14.Marzo.16.Ejercicio
### importar la matriz del inegi
indi3 <- ts(read.csv(("C:\\Users\\SALA-C16\\Documents\\Tasas.csv"), 
                     header = T), frequency = 4, start = 2005)
class(indi3)
desoparcial<-ts(indi3[,1],start=2005, freq=4)
asala<-ts(indi3[,2], start=2005, freq=4)
til1<-ts(indi3[,3],start=2005, freq=4)
seriemultiple<-ts.intersect(desoparcial,asala,til1) ### Serie de tiempo multiple
plot(seriemultiple, main="Serie de tiempo multiple", xlab="Años", ylab="Numero de personas",
     col="blue")
seriemultiple

### Separar la serie de tiempo dependiendo del analisis
seriemultiple05.09<-window(seriemultiple, start=c(2005,1), end=c(2009,4))
seriemultiple10.12<-window(seriemultiple, start=c(2010,1), end=c(2015,4))
layout(1:2)
plot(seriemultiple05.09, main="Serie de tiempo multiple", xlab="Años", ylab="Numero de personas",
     col="red")
plot(seriemultiple10.12, main="Serie de tiempo multiple", xlab="Años", ylab="Numero de personas",
     col="blue")
start(seriemultiple); end(seriemultiple)

### Ejercicio
### 1) Importar base
### 2) Declarar serie de tiempo
### 3) Graficar las variables separadas
### 4) Graficar juntas como serie de tiempo
### 5) Crear serie de tiempo multiple
### importar la matriz de las acciones de Bimbo
bimbo <- ts(read.csv(("C:\\Users\\SALA-C16\\Documents\\Bimbo.csv"), 
                     header = T), frequency = 12, start = 2000)
bimbo
class(bimbo)
open<-ts(bimbo[,1],start=2000, freq=12)
plot(open, main="Precio de apertura", xlab="Fecha", ylab="Precio",
       col="blue")
close<-ts(bimbo[,2],start=2000, freq=12)
plot(close, main="Precio de cierre", xlab="Fecha", ylab="Precio",
       col="blue2")
volumen<-ts(bimbo[,3],start=2000, freq=12)
plot(volumen, main="Volúmen", xlab="Fecha", ylab="Precio",
       col="blue3")
serieb <-ts.intersect(open,close,volumen) ### Serie de tiempo multiple
plot(serieb, main="Serie multiple", xlab="Fecha", ylab="Precio",
     col="blue")
seriemultiple

### Separar la serie de tiempo dependiendo del analisis
serieb02.08<-window(serieb, start=c(2002,1), end=c(2008,12))
serieb09.15<-window(serieb, start=c(2009,1), end=c(2015,12))
layout(1:2)
plot(serieb02.08, main="Serie multiple", xlab="Años", ylab="Precio",
     col="red")
plot(serieb09.15, main="Serie multiple", xlab="Años", ylab="Precio",
     col="blue")

start(seriemultiple); end(seriemultiple)
