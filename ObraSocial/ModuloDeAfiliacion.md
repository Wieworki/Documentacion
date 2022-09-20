# Alcance del módulo

El módulo de afiliación fue heredado del grupo de programadores anterior. Es un módulo relativamente pequeño,
conteniendo más que nada algunos ABM para algunas entidades. Permite la carga y modificación de personas que estén
afiliadas a la obra social, y sus familiares. Está estrechamente vinculado con el módulo de órdenes médicas, ya que éste
toma datos de los afiliados.

## Usuarios del sistema

El módulo de afiliación debe permitir dos tipos de interacciones: la carga de nuevos afiliados, y la consulta de los mismos.

**Diagrama de casos de uso**

![imagen](https://user-images.githubusercontent.com/45775681/190910540-4ff3ddbd-5335-407a-b1fd-85b15b62b3d2.png)

### Operador de consulta

Refiere a los usuarios con roles de consulta. Nuclea a todos los usuarios del módulo de órdenes médicas,
que por algún motivo deban buscar información sobre algún afiliado a la obra social. Solamente pueden consultar
la información cargada, sin tener la posibilidad de cargar nuevas personas ni modificar las existentes

### Operador de carga

Refiere a los operadores encargados de mantener el padrón de afiliados actualizado.
Pueden modificar la información cargada, y cargar nuevas personas al sistema.

## Entidades

### Persona

Entidad padre, de la que heredan las entidades "Titular" y "Familiar". Nuclea todas las propiedades
que son comunes para estas dos entidades hijas. Cuenta con la siguiente información:

- id
- nro_doc
- tp_doc
- cuil
- nombre
- sexo
- direccion
- id_cpostal
- incapacidad
- estado_civil
- telefono
- fec_nacimiento
- fec_alta
- obs
- estado

Una persona que esté en estado "inactivo", sigue registrada en el sistema, pero es considerada como dada de baja de la obra social.
Esto implica que no es posible emitirle órdenes médicas desde el módulo de órdenes.

### Titular

Entidad que refiere a la persona que está afiliada a la obra social. Hereda todas los atributos de la entidad "Persona"
Cuenta con la siguiente información:

- id
- id_persona
- id_categoria
- provincia
- dpto
- mail
- nacionalidad
- cbu
- aporta_sc (si paga servicios sociales)
- nro_afiliacion
- fec_baja
- fec_afiliacion
- fec_ingreso
- fec_caduca
- tipo_empleo
- id_empresa
- id_convenio
- afiliado  (Puede estar afiliado solo a la obra social, solo al gremio, o a ambos)
- fin_delegacion (si es delegado gremial, tiene una fecha de fin)

### Familiar

Entidad que refiere a una persona que es familiar de un titular de la obra social. Hereda todos los atributos de la entidad "Persona"
Cuenta con la siguiente información:

- id
- id_persona
- id_titular
- vinculo
- documentacion_completa
- extension_afiliacion (años que se le extiende la cobertura más allá del tope)

Los familiares de un titular se diferencian según el vínculo que tengan hacia el mismo.
Para el caso particular de los *hijos* de un titular, los mismos tendrán cobertura hasta que cumplan 21 años, en cuyo caso son dados
de baja automáticamente por el sistema, pasando los mismos a estado "inactivo". Se puede extender la cobertura por 1 año más, siendo el tope
de extensión los 25 años, mediante la presentación de un certificado de estudios superiores de forma anual.
