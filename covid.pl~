:-use_module(library(pce)).
:-pce_image_directory('./Img').

resource(covid,image,image('covid.jpg')).
resource(covid2,image,image('covid2.jpg')).
resource(prueba,image,image('prueba.jpg')).
resource(calavera,image,image('calavera.jpg')).
resource(enfermo,image,image('enfermo.jpg')).
resource(leve,image,image('leve.jpg')).
resource(negativo,image,image('negativo.jpg')).
resource(medidasImg,image,image('medidas.jpeg')).
iniciar:-
    new(Inicio,dialog('Sistema experto Covid-19',size(700,700))),
    new(Titulo, text('Sistema experto para el diagnostico de Covid-19')),
    send(Titulo,font,bold),
    send(Titulo,alignment,center),
    send(Titulo,colour,'#ff2424'),
    send(Inicio,append,Titulo),
    new(Boton_info,button('MÓDULO DE INFORMACIÓN',and(message(@prolog,informacion)))),
    new(Boton_diag,button('INICIAR DIAGNÓSTICO',and(message(@prolog,diag)))),
    send(Inicio,append,Boton_info),
    send(Inicio,append,Boton_diag),
    nueva_imagen(Inicio,covid,20,70),

    send(Inicio,open).

nueva_imagen(Ventana,Imagen,X,Y):-
    new(Figura, figure),
    new(Bitmap, bitmap(resource(Imagen),@on)),
    send(Bitmap,name,1),
    send(Figura, display, Bitmap),
    send(Figura, status, 1),
    send(Ventana, display, Figura, point(X,Y)).

informacion:-
    new(Info,dialog('Información sobre Covid-19',size(900,900))),
    new(Titulo2,text('Información importante sobre la Covid-19')),
    send(Titulo2,font,bold),
    send(Titulo2,alignment,center),
    send(Titulo2,colour,'#ff2424'),
    new(Quees,text(
'Los coronavirus son una familia de virus que causan enfermedades
(desde el resfriado común hasta enfermedades respiratorias más graves)
y circulan entre humanos y animales.
En este caso, se trata del SARS-COV2. Apareció en China en diciembre
pasado y provoca una enfermedad llamada COVID-19, que se extendió por
el mundo y fue declarada pandemia global por la Organización Mundial
de la Salud.')),
    send(Quees,alignment,center),
    send(Quees,colour,'#000000'),
    send(Quees,font,bold),
    send(Info,append,Titulo2),
    send(Info,append,Quees),
    new(Boton_medidas,button('CONOCER LAS MEDIDAS DE PREVENCIÓN',and(message(@prolog,medidas)))),
    send(Info,append,Boton_medidas),
    nueva_imagen(Info,covid2,20,200),
    send(Info,open)
    .
medidas:-
    new(Medidas,dialog('Medidas de prevención')),
    nueva_imagen(Medidas,medidasImg,0,0),
    send(Medidas,open).

diag:-
    new(Principal1, dialog('Sistema Experto Covid-19')),
    new(Titulo, text('Sistema Experto para la detección de la enfermedad \n del Covid-19')),
    send(Titulo,font,bold),
    send(Titulo,alignment,center),
    send(Titulo,colour,"#ff2424"),
    send(Principal1,append,Titulo),
    new(Nombre,text_item(nombre_del_paciente)),
    send(Principal1,append,Nombre),
    %Creamos las etiquetas para cada pregunta
    new(Pregunta1,text('¿Presenta hipoxia(Oxigenación baja en la sangre) y no se atribuye al ambiente?')),
    send(Pregunta1,alignment,left),
    send(Pregunta1,font,bold),

    new(Pregunta2,text('¿Presenta dificultad para respirar y no tiene alguna enfermedad crónica?')),
    send(Pregunta2,alignment,left),
send(Pregunta2,font,bold),

    new(Pregunta3,text('¿Presenta dificultad para concentrarse y no es por insomnio?')),
    send(Pregunta3,alignment,left),
send(Pregunta3,font,bold),

    new(Pregunta4,text('¿Presenta fiebre?')),
    send(Pregunta4,alignment,left),
send(Pregunta4,font,bold),


    new(Pregunta5,text('¿Presenta fatiga?')),
    send(Pregunta5,alignment,left),
send(Pregunta5,font,bold),

new(Pregunta6,text('¿Presenta mareos?')),
    send(Pregunta6,alignment,left),
send(Pregunta6,font,bold),

new(Pregunta7,text('¿Presenta pérdida de olfato?')),
    send(Pregunta7,alignment,left),
send(Pregunta7,font,bold),

new(Pregunta8,text('¿Presenta conjuntivitis?')),
    send(Pregunta8,alignment,left),
    send(Pregunta8,font,bold),


new(Pregunta9,text('¿Presenta aparición de erupción cutánea?')),
    send(Pregunta9,alignment,left),
send(Pregunta9,font,bold),

new(Pregunta10,text('¿Manifiesta dolor en las articulaciones?')),
    send(Pregunta10,alignment,left),
send(Pregunta10,font,bold),

new(Pregunta11,text('¿Presenta dolor de cabeza?')),
    send(Pregunta11,alignment,left),
send(Pregunta11,font,bold),

new(Pregunta12,text('¿Presenta dolor de garganta?')),
    send(Pregunta12,alignment,left),
send(Pregunta12,font,bold),

new(Pregunta13,text('¿Presenta escalofrios?')),
    send(Pregunta13,alignment,left),
send(Pregunta13,font,bold),

new(Pregunta14,text('¿Manifiesta diarrea?')),
    send(Pregunta14,alignment,left),
send(Pregunta14,font,bold),


    %listas para las respuestas
    new(R_1,menu('',cycle)),
    new(R_2,menu('',cycle)),
    new(R_3,menu('',cycle)),
    new(R_4,menu('',cycle)),
    new(R_5,menu('',cycle)),
    new(R_6,menu('',cycle)),
    new(R_7,menu('',cycle)),
    new(R_8,menu('',cycle)),
    new(R_9,menu('',cycle)),
    new(R_10,menu('',cycle)),
    new(R_11,menu('',cycle)),
    new(R_12,menu('',cycle)),
    new(R_13,menu('',cycle)),
     new(R_14,menu('',cycle)),
    %Agregamos el tipo de respuesta valida es decir SI o NO

    Respuestas_validas = ['NO','SI'],

    send_list(R_1, append, Respuestas_validas),
    send_list(R_2, append, Respuestas_validas),
    send_list(R_3, append, Respuestas_validas),
    send_list(R_4, append, Respuestas_validas),
    send_list(R_5, append, Respuestas_validas),
    send_list(R_6, append, Respuestas_validas),
    send_list(R_7, append, Respuestas_validas),
    send_list(R_8, append, Respuestas_validas),
    send_list(R_9, append, Respuestas_validas),
    send_list(R_10, append, Respuestas_validas),
    send_list(R_11, append, Respuestas_validas),
    send_list(R_12, append, Respuestas_validas),
    send_list(R_13, append, Respuestas_validas),
     send_list(R_14, append, Respuestas_validas),

    %Generamos un grupo de elementos de las preguntas

    new(Grupo_de_preguntas, dialog_group(texts,group)),
    send(Grupo_de_preguntas, gap, size(0,20)),

    %Enviamos cada pregunta al grupo correspondiente

    send(Grupo_de_preguntas, append, Pregunta1),
    send(Grupo_de_preguntas, append, Pregunta2),
    send(Grupo_de_preguntas, append, Pregunta3),
    send(Grupo_de_preguntas, append, Pregunta4),
    send(Grupo_de_preguntas, append, Pregunta5),
    send(Grupo_de_preguntas, append, Pregunta6),
    send(Grupo_de_preguntas, append, Pregunta7),
    send(Grupo_de_preguntas, append, Pregunta8),
    send(Grupo_de_preguntas, append, Pregunta9),
    send(Grupo_de_preguntas, append, Pregunta10),
    send(Grupo_de_preguntas, append, Pregunta11),
    send(Grupo_de_preguntas, append, Pregunta12),
    send(Grupo_de_preguntas, append, Pregunta13),
    send(Grupo_de_preguntas, append, Pregunta14),

    send(Principal1,append,Grupo_de_preguntas),

    new(Grupo_de_respuestas, dialog_group(menus,group)),
    send(Grupo_de_respuestas, gap, size(0, 11)),

    send(Grupo_de_respuestas, append, R_1),
    send(Grupo_de_respuestas, append, R_2),
    send(Grupo_de_respuestas, append, R_3),
    send(Grupo_de_respuestas, append, R_4),
    send(Grupo_de_respuestas, append, R_5),
    send(Grupo_de_respuestas, append, R_6),
    send(Grupo_de_respuestas, append, R_7),
    send(Grupo_de_respuestas, append, R_8),
    send(Grupo_de_respuestas, append, R_9),
    send(Grupo_de_respuestas, append, R_10),
    send(Grupo_de_respuestas, append, R_11),
    send(Grupo_de_respuestas, append, R_12),
    send(Grupo_de_respuestas, append, R_13),
    send(Grupo_de_respuestas, append, R_14),

    send(Principal1, append, Grupo_de_respuestas, right),

    new(Boton_evaluar,button('DIAGNOSTICAR',and(message(@prolog,evaluar,
                                                        R_1?selection,
                                                        R_2?selection,
                                                        R_3?selection,
                                                        R_4?selection,
                                                        R_5?selection,
                                                        R_6?selection,
                                                        R_7?selection,
                                                        R_8?selection,
                                                        R_9?selection,
                                                        R_10?selection,
                                                        R_11?selection,
                                                        R_12?selection,
                                                        R_13?selection,
                                                        R_14?selection,
                                                       Nombre?selection)))),
    send(Principal1, append, Boton_evaluar),

    send(Principal1,open).

evaluar(R_1,R_2,R_3,R_4,R_5,R_6,R_7,R_8,R_9,R_10,R_11,R_12,R_13,R_14,Nombre):-
    abrir_conexion,
    new(Respuesta, dialog('INFERENCIA')),

    new(Titulo2,text('Nuestro diagnostico es: ')),
    send(Titulo2,font,bold),
    send(Titulo2,alignment,center),
    send(Titulo2,colour,'#ff2424'),

    %Obtenemos el valor de cada respuesta
    get(Nombre,value,Name),
    get(R_1,value,Res_1),
    get(R_2,value,Res_2),
    get(R_3,value,Res_3),
    get(R_4,value,Res_4),
    get(R_5,value,Res_5),
    get(R_6,value,Res_6),
    get(R_7,value,Res_7),
    get(R_8,value,Res_8),
    get(R_9,value,Res_9),
    get(R_10,value,Res_10),
    get(R_11,value,Res_11),
    get(R_12,value,Res_12),
    get(R_13,value,Res_13),
    get(R_14,value,Res_14),

    (covid(Res_1,Res_2,Res_3)->nueva_imagen(Respuesta,calavera,20,40),new(Salida,text('
Estimado usuario, usted está contagiado de COVID-19.
Los síntomas que usted presenta son graves y requieren de una atención medica inmediata,
le recomendamos rotundamente acudir a su medico y seguir las medidas de prevención,
dichas recomendaciones las puede encontrar en nuestro módulo de información.  ')),
     send(Salida,font,bold),send(Salida,alignment,center),

     ingresar_registro(Name,'Usted tiene covid-19',F),
      atom_concat('Registros guardados en la base de datos: ',F,R),
     new(Afect,text(R))

      ;
    (   alto(Res_4,Res_5)->nueva_imagen(Respuesta,enfermo,20,40),new(Salida,text('
Estimado usuario, usted posee síntomas muy característicos de COVID-19,
existe un índice bastante alto de que usted sea portador de esta,
nuestra recomendación es seguir las medidas de prevención que puede
encontrar en nuestro módulo de información y realizarse una prueba
PCR o, en su defecto, de antígenos para verificar su resultado.
En caso de ser positivo, acuda de inmediato a su médico.
')),
        send(Salida,font,bold),send(Salida,alignment,center),
        ingresar_registro(Name,'Usted riesgo alto de padecer Covid',F),
         atom_concat('Registros guardados en la base de datos: ',F,R),
     new(Afect,text(R))
        ;
    (  medio(Res_6,Res_7,Res_8,Res_9,Res_10,Res_11,Res_12,Res_13,Res_14)->nueva_imagen(Respuesta,leve,20,40),new(Salida,text('
Estimado usuario, usted posee síntomas leves de COVID-19, es posible que usted sea portador
de esta enfermedad por lo cual le recomendamos seguir las medidas de prevención que se
encuentran disponibles en nuestro módulo de información, así como realizarse una prueba
de antígenos para verificar los resultados, si el resultado es positivo, entonces acuda a
su médico siguiendo las medidas de prevención.
')),
       send(Salida,font,bold),send(Salida,alignment,center),
       ingresar_registro(Name,'Usted riesgo bajo de padecer Covid',F),
        atom_concat('Registros guardados en la base de datos: ',F,R),
     new(Afect,text(R))
       ;
    nueva_imagen(Respuesta,negativo,20,40),
       ingresar_registro(Name,'Usted no tiene Covid',F),
        atom_concat('Registros guardados en la base de datos: ',F,R),
     new(Afect,text(R)),
    new(Salida,text('
Estimado usuario, usted no posee ninguno de los síntomas, por lo tanto
no es portador de esta enfermedad, sin embargo, recomendamos seguir las
medidas preventivas para prevenir la propagación y evitar contagios.')),send(Salida,font,bold),send(Salida,alignment,center)))),
    send(Respuesta,append,Titulo2),
    send(Respuesta,append,Salida),
    send(Respuesta,append,Afect),
    new(Boton_info,button('Informacion',and(message(@prolog,informacion)))),
    send(Respuesta,append,Boton_info),
    cerrar_conexion,
    send(Respuesta,open).


covid(Res_1,Res_2,Res_3):-
    (   Res_1 == 'SI';
    Res_2 == 'SI';
    Res_3 == 'SI').

alto(Res_4,Res_5):-
    (   Res_4 == 'SI';
    Res_5 == 'SI')
    .

medio(Res_6,Res_7,Res_8,Res_9,Res_10,Res_11,Res_12,Res_13,Res_14):-
    (   Res_6 == 'SI';
    Res_7 == 'SI';
    Res_8 == 'SI';
    Res_9 == 'SI';
    Res_10 == 'SI';
    Res_11 == 'SI';
    Res_12 == 'SI';
    Res_13 == 'SI';
    Res_14 == 'SI'
    )
    .

abrir_conexion:-
    odbc_connect('MSProlog',_,
                 [user(root),
                  password(''),
                  alias(prolog),
                  open(once)]).

cerrar_conexion:-
    odbc_disconnect('prolog').

consultar_registro(F):-

        odbc_query('prolog',
               'SELECT * FROM persona',F).
concatenar(A,B,C):-
    atom_concat('INSERT INTO persona (nombre,diagnostico) VALUES ("',A,D),
    atom_concat(D,'","',E),
    atom_concat(E,B,F),
    atom_concat(F,'")',C).
ingresar_registro(Nombre,Diagnostico,F):-
     concatenar(Nombre,Diagnostico,C),
    odbc_query('prolog',
              C,affected(F)).


