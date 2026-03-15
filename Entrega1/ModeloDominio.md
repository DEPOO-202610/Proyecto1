**LINK\_MERMAID** = https://mermaid.live/edit#pako:eNqFVd1O2zAUfpXIl6hUpE2hjRBSSUFigoH42cWUGzc5Tb0lPpHjsAHjofYMe7GdxE0ap3TLlX1-vvP5nM\_OG4swBuazKOVFsRA8UTwLZSjrvfNUlFwJdN5C6dD3oJWQiZNiIqRlySn4B6o4lO\_b5CAVIDU0ydei0M63EhIsLvkzKqGxMB4htZOXkvaXIoZUxNwGusjyFHjcp6FLJfEBMi55ahwxlssUnBiKqKTSaKHM40xI4qAISVVQHd8NFKDwA6YBSoxEXDHtnoxscpPQMX-qUnokJWZLBdtz8j-\_8Y5YiohHAu0uQpYrKPgNp-2r8QRcE6YS3GBHzdbOKzSdyZiWiNQrSbaFWIlIpBbDK\_lMfflgpFrkuCUZcamrKSxEkaMU1FML5U5VFbMWY0GsnBVEa954-vYFPGNa7h54Q9zCxriMNAZ8BRropL0en8OSmDWVt6edpxGusWpr3xNwo0O7DC80pA1-O3ROpgRkb9ykjjas2547UAVKXtgVNVWDGwKhXkz2u9ypVeNLNZfdhlq6FlleUst67BageZqCBdBlaUGQwGgKT1LUIrBFbUttg3R6CrLMQHFNwzs726hyfv84fzDrx\_n59cX9rdnMg-Dq9vMGtnk8Tn8dHjaPQc\_a3Oye2bqqFVT7AtRuc1v71uZSVvG7KqpDjHj2ureiqDCa5ytkbsgccofsaDg8oHWrf99RQOp6rSE3tk54tTDN9GkiUVq-wP7AWmS-g1GpFFzIikFt6oaZ8g2xOjivudpvWyfloEMhocI0RP6f8M4b4Tu8jazKdFx7akQoa5HvaWAVaoTaaZ0x9KIsVXfaZ9lNaNvC3bH6JHhj25Y5-EfX2YAlSsTM16qEASPdZ7zasvo2hEyvIYOQ-bSMufoeMpI65eRcfkXMmjSFZbJm\_oqnBe3KPKabtfm1tiEgY1AB0l-P-dPpqMZg\_hv7yXzPHY6PpzPPPZ6MR9OZO\_YG7IX5h6PhxJ2409nEPfJmE-\_EO3kfsNe6LmV47snRZDo6no1HR57rvf8F55qsOQ





# **# Modelo de Dominio - Board Game Café**



classDiagram



class Usuario {

&#x20;   String login

&#x20;   String password

}



class Cliente {

&#x20;   List juegosFavoritos

&#x20;   int puntosFidelidad

}



class Empleado {

&#x20;   String turnoSemanal

&#x20;   double descuento

}



class Administrador {

}



class Mesero {

&#x20;   List juegosConocidos

}



class Cocinero {

}



class Juego {

&#x20;   String nombre

&#x20;   int añoPublicacion

&#x20;   String empresaMatriz

&#x20;   CategoriaJuego categoria

&#x20;   String estado

&#x20;   boolean esDificil

}



class Inventario {

&#x20;   String tipo

&#x20;   int cantidadDisponible

}



class Prestamo {

&#x20;   Date fechaPrestamo

&#x20;   Date fechaDevolucion

&#x20;   String estado

}



class ProductoCafeteria {

}



class Bebida {

&#x20;   boolean esAlcoholica

&#x20;   boolean esCaliente

}



class Pasteleria {

&#x20;   List alergenos

}



class Mesa {

&#x20;   int cantidadPersonas

&#x20;   boolean tieneMenores5

&#x20;   boolean tieneMenores18

}



class Venta {

&#x20;   Date fecha

&#x20;   double impuestos

}



class DetalleVenta {

&#x20;   int cantidad

&#x20;   double precioUnitario

}



class CategoriaJuego {

&#x20;   <<enumeration>>

&#x20;   CARTAS

&#x20;   TABLERO

&#x20;   ACCION

}



Usuario <|-- Cliente

Usuario <|-- Empleado

Usuario <|-- Administrador



Empleado <|-- Mesero

Empleado <|-- Cocinero



ProductoCafeteria <|-- Bebida

ProductoCafeteria <|-- Pasteleria



Cliente "1" -- "0..\*" Prestamo : realiza

Prestamo "1" -- "1" Juego : incluye

Prestamo "1" -- "1" Mesa : ocurreEn



Mesa "1" -- "1..\*" Cliente : ocupa



Administrador "1" -- "\*" Juego : gestiona

Administrador "1" -- "\*" Inventario : administra



Inventario "1" -- "\*" Juego : contiene



Cliente "1" -- "\*" Venta : realiza

Venta "1" -- "\*" DetalleVenta : incluye

DetalleVenta "\*" -- "1" ProductoCafeteria : producto

Venta "\*" -- "1" Mesa : ocurren





