# SpringBoot_Rest

Postgres tables creation

CREATE TABLE public.persona
(
    id integer NOT NULL GENERATED ALWAYS AS IDENTITY ( INCREMENT 1 START 1 MINVALUE 1 MAXVALUE 2147483647 CACHE 1 ),
    nombre varchar(100),
    apellido varchar(100),
    direccion varchar(80),
    telefono varchar(30),
    CONSTRAINT persona_primary_key PRIMARY KEY (id)
)


CREATE TABLE public.automovil
(
    id integer NOT NULL,
    marca varchar(80) COLLATE pg_catalog."default",
    color varchar(50) COLLATE pg_catalog."default",
    modelo varchar(50) COLLATE pg_catalog."default",
    persona_id integer NOT NULL,
    CONSTRAINT automovil_primary_key PRIMARY KEY (id),
    CONSTRAINT persona_foreign_key FOREIGN KEY (persona_id) REFERENCES public.persona (id)
)
