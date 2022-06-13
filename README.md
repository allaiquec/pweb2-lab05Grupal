<div align="center">
<table>
    <theader>
        <tr>
            <td><img src="https://github.com/rescobedoq/pw2/blob/main/epis.png?raw=true" alt="EPIS" style="width:50%; height:auto"/></td>
            <th>
                <span style="font-weight:bold;">UNIVERSIDAD NACIONAL DE SAN AGUSTIN</span><br />
                <span style="font-weight:bold;">FACULTAD DE INGENIERÍA DE PRODUCCIÓN Y SERVICIOS</span><br />
                <span style="font-weight:bold;">ESCUELA PROFESIONAL DE INGENIERÍA DE SISTEMAS</span>
            </th>
            <td><img src="https://github.com/rescobedoq/pw2/blob/main/abet.png?raw=true" alt="ABET" style="width:50%; height:auto"/></td>
        </tr>
    </theader>
    <tbody>
        <tr><td colspan="3"><span style="font-weight:bold;">Formato</span>: Guía de Práctica de Laboratorio / Talleres / Centros de Simulación</td></tr>
        <tr><td><span style="font-weight:bold;">Aprobación</span>:  2022/03/01</td><td><span style="font-weight:bold;">Código</span>: GUIA-PRLE-001</td><td><span style="font-weight:bold;">Página</span>: 1</td></tr>
    </tbody>
</table>
</div>

<div align="center">
<span style="font-weight:bold;">INFORME DE LABORATORIO</span><br />

<table>
<theader>
<tr><th colspan="6">INFORMACIÓN BÁSICA</th></tr>
</theader>
<tbody>
<tr><td>ASIGNATURA:</td><td colspan="5">Progamación Web 2</td></tr>
<tr><td>TÍTULO DE LA PRÁCTICA:</td><td colspan="5">Django</td></tr>
<tr>
<td>NÚMERO DE PRÁCTICA:</td><td>05</td><td>AÑO LECTIVO:</td><td>2022 A</td><td>NRO. SEMESTRE:</td><td>III</td>
</tr>
<tr>
<td>FECHA DE PRESENTACIÓN:</td><td>12/06/2022</td><td>HORA DE PRESENTACIÓN:</td><td colspan="3">11:55 pm</td>
</tr>
<tr><td colspan="3">INTEGRANTE(s):
<ul>
    <li>Contreras Mamani Claudia Asunción - ccontrerasma@usa.edu.pe</li>
    <li>Cordova Silva Heidi Stephany - hcordovas@unsa.edu.pe</li>
    <li>Llaique Chullunquia Angie Carolina - allaiquec@unsa.edu.pe</li>
    <li>Mamani Cañari Gabriel Antony - gmamanican@unsa.edu.pe</li>
</ul>
</td>
<td>NOTA:</td><td colspan="2"></td>
</<tr>
<tr><td colspan="6">DOCENTE(s):
<ul>
<li>Richart Smith Escobedo Quispe - rescobedoq@unsa.edu.pe</li>
</ul>
</td>
</<tr>
</tbody>
</table>

<table>
<theader>
<tr><th>Solución y resultados</th></tr>
</theader>
<tbody >
<tr><td>I. SOLUCIÓN DE EJERCICIOS/PROBLEMAS
    <ul>
        <li>Todos realizamos nuestros propios blogs siguiendo el tutorial dado, sin embargo, para la entrega decidimos usar uno y mejorarlo en conjunto para hacer la presentación mediante una reunión meet<br/>
        <image src="https://user-images.githubusercontent.com/85516522/173279989-454b15ed-37b2-4597-a4cc-765c0cf913d7.png" width=500/>
        </li>
        <li>URL pública del blog: https://gabicho.pythonanywhere.com/</li>
        <li>Video explicativo: https://www.youtube.com/watch?v=BYaMvbQ7mc0</li>
        <li>Los ejercicios se realizaron en un ambiente virtual. Siga los siguientes pasos para poder ejecutar el blog: 
            <ol>
                <li>Clonar el repositorio</li>
                <li>Acceder al repositorio <code>cd pweb2-lab05Grupal</code></li>
                <li>Crear un ambiente virtual en el repositorio con <code>virtualenv -p python3 .</code></li>
                <li>Active el ambiente virtual con <code>./bin/activate</code> en linux y <code>./Scripts/activate</code> en Windows</li>
                <li>Instalar las dependencias con <code>pip install -r requirements.txt</code></li>
                <li>Ya podrá ejecutar el blog</li>
            </ol>
        </li>
        <li>
            Pasos para realizar el trabajo, de manera breve, realizamos:
            <ol>
                <li>Creamos nuestro directorio donde guardaremos el proyecto</li>
                <li>En el directorio, creamos nuestro ambiente virtual y lo iniciamos</li>
                <li>Instalamos Django <code>pip install Django==3.2.10</code>. Usamos esta versión porque es la máxima soportada por pythonanywere<li/>
                <li>Inicializamos el proyecto con <code>django-admin startproject mysite .</code></li>
                <li>
                    Realizamos las configuraciones:
                    <ol>
                        <li>
                            Abrimos el archivo mysite/settings.py y cambiamos:
                            <ol>
                                <li>TIME_ZONE=’America/Lima’</li>
                                <li>LANGUAGE_CODE = 'es-es'</li>
                                <li>STATIC_URL = '/static/'</li>
                                <li>STATIC_ROOT = os.path.join(BASE_DIR, 'static')</li>
                                <li>ALLOWED_HOSTS = ['127.0.0.1', '.pythonanywhere.com']</li>
                                <li>La base de datos vendrá configurado por defecto.</li>
                            </ol>
                        </li>
                        <li>Ejecutamos <code>python manage.py migrate</code> para aplicar los cambios hechos</li>
                    </ol>
                </li>
                <li>Una vez realizadas las configuraciones, podremos iniciar el servidor con <code>Python manage.py runserver</code></li>
                <li>Una vez vimos la ejecución fue exitosa, procedimos a crear nuestra aplicación con <code>python manage.py startapp blog</code></li>
                <li>Nuevamente abrir los mysite/settings y añadimos nuestra app al arreglo <code> INSTALLED_APPS=[……, 'blog.apps.BlogConfig', ]</code></li>
                <li>Luego abrimos blog/models.py y creamos nuestro modelo Post</li>
                <li>Una vez creado el modelo, haremos que se cree la tabla en la base de datos con <code>python manage.py makemigrations</code> y luego <code>python manage.py migrate</code></li>
                <li>Luego creamos un superusuario para poder añadir Post momentáneos con <code>python manage.py createsuperuser</code></li>
                <li>Luego subimos nuestro proyecto a GitHub, pero primero realizamos un .gitignore para no subir cahché ni elementos del virtual environment.</li>
                <li>Una vez subido, nos creamos una cuenta en www.pythonanywhere.com para poder subir nuestro proyecto, en la Shell de pythonanywhere instalamos la dependencia de pythonanywhere, el proyecto lo instalamos con <code>pa_autoconfigure_django.py --python=3.6 url_repositorio</code></li>
                <li>Viendo que funcionaba, hicimos una plantilla html en blog/templates/blog, creamos una vista en blog/views.py que renderice esta plantilla y configuramos las urls en blog/urls.py para que muestre la vista.</li>
                <li>Luego usamos QuerySets, las enviamos a través del contexto ({}) para poder usarlo dinámicamente en el HMTL.</li>
                <li>Ya sabiendo manejar el contexto y y a insertar código python en HTML, gracias Django, utilizamos templates base para reutilizar código HTML.</li>
                <li>Creamos un archivo Forms.py para poder realizar un formulario para crear nuevos Posts y le pusimos validaciones para que solo super usuarios registrados puedan crear. </li>
                <li>Luego instalamos Pillow~=9.1.1 como dependencia, esta librería nos fue útil para poder agregarle imagen a nuestro blog. </li>
                <li>
                    Creamos rutas estáticas para las imágenes en settings: 
                    <ol>
                        <li>MEDIA_ROOT = os.path.join(BASE_DIR, 'blog/media')</li>
                        <li>MEDIA_URL = 'blog/media/'</li>
                    </ol>
                </li>
                <li>
                    Luego modificamos el modelo y las url para poder hacer uso de estas rutas y poder subir imágenes desde el front    
                    <ol>
                        <li>En blog/urls.py añadimos <code>urlpatterns += static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)</code></li>
                        <li>En el modelo de Post añadimos <code>photo = models.ImageField(upload_to='images/', blank=True, null=True)</code></li>
                        <li>Y finalmente en blog/views cambiamos de <code>form = PostForm(request.POST)</code> a <code>form = PostForm(request.POST, request.FILES)</code> para poder recibir los documentos enviados.</li>
                    </ol>
                </li>
                <li>Finalmente le dimos estilos a toda la aplicación para la presentación.</li>
            </ol>
        </li>
    </ul>
<tr><td>II. SOLUCIÓN DEL CUESTIONARIO
    <ul>
        <li>
            ¿Cuál es un estándar de codificación para Python?
            <ul>
                <li>Un estándar de codificación para Python es PEP8.</li>
                <li>La comunidad de usuarios de Python ha adoptado una guía de estilo que facilita la lectura del código y la consistencia entre programas de distintos usuarios.</li>
                <li>PEP8 sirve para escribir código claro y comprensible para otros programadores dando recomendaciones con el objetivo de escribir un código más legible.</li>
                <li>En esta se define al pie de la letra, como debería estar escrito nuestro código Python. Ver más en https://ellibrodepython.com/python-pep8 .</li>
            </ul>  
        </li>
        <li>
            ¿Qué diferencias existen entre EasyInstall, pip, y PyPM?
            <ul>
                <li>
                    EasyInstall
                    <ul>
                        <li>Suministra un formato estándar para distribuir programas y bibliotecas en Python</li>
                        <li>Solo hay easy_install en la versión anterior de Python</li>
                        <li>Es gratuito</li>
                        <li>Viene por defecto en las setuptools</li>
                    </ul>
                </li>
                <li>
                    Pip
                    <ul>
                        <li>Permite gestionar listas de paquetes y sus números de versión correspondientes a través de un archivo de requisitos</li>
                        <li>Pip es una versión mejorada de easy_install</li>
                        <li>Es gratuito</li>
                        <li>Se debe instalar para las versionas anteriores a Python 3.4, en las posteriores incluyen pip por defecto.</li>
                    </ul>
                </li>
                <li>
                    PyPM
                    <ul>
                        <li>Simplifica las tareas de localización, instalación, actualización y eliminación de paquetes de Python</li>
                        <li>PyPM no es gratuito y solo se puede usar con la distribución ActivePython de ActiveState</li>
                        <li>Se debe instalar manualmente</li>
                    </ul>
                </li>
            </ul>
        </li>
        <li>
            En un proyecto Django que se debe ignorar para usar git. Vea: https://github.com/django/django/blob/main/.gitignore. ¿Qué otros tipos de archivos se deberían agregar a este archivo?
            <ul>
                <li>
                    Ejmplo: 
                    <ul>
                        <li>*.pyc</li>
                        <li>*~</li>
                        <li>__pycache__</li>
                        <li>myvenv</li>
                        <li>db.sqlite3</li>
                        <li>.DS_Store</li>
                        <li>include/</li>
                        <li>lib/</li>
                        <li>src/__pycache__</li>
                        <li>bin/</li>
                        <li>Scripts/ </li>
                        <li>pyvenv.cfg</li>
                    </ul>
                </li>
                <li>Al ignorar la base de datos SQLite en tu copia de GitHub, todos los posts y el super usuario que has creado hasta el momento solo estarán disponibles en local, y tendrás que crear nuevos usuarios y publicaciones en producción. Tu base de datos local es un buen campo de pruebas.</li>
            </ul>
        </li>
        <li>
            Utilice <code>python manage.py shell</code> para agregar objetos. ¿Qué archivos se modificaron al agregar más objetos?
            <ul>
                <li>Para crear un nuevo objeto Post, necesitamos un autor, el cual podemos sacar de uno de los post anteriores, o podemos ver todos los usuarios tenemos en nuestra base de datos.</li>
                <li>Obtenemos una instancia del usuario.</li>
                <li>Con ello, recién podemos crear nuestro nuevo objeto Post</li>
                <li>Finalmente, podemos ver si está guardado con Post.objects.all(), donde vemos que se ha actualizado. </li>
                <li>Entonces se puede decir que el archivo modificado, al usar python manage.py shell para agregar objetos, es la base de datos que viene por defecto, sqlite3, que se  encuentra configurado en mysite/settings.py</li>
            </ul>
        </li>
    </ul>
    </td></tr>
<tr><td>III. CONCLUSIONES
    <ul>
        <li>La guía: https://tutorial.djangogirls.org/es/django_start_project/ nos ha servido para introducirnos en el proceso de creación de un blog usando django, incluso siendo un blog básico hemos aprendido mucho.</li>
        <li>En conclusión Django es uno de los Frameworks de Python más populares, que da recursos para la creación de aplicaciones y estos se pudo emplear para las necesidades de este proyecto de creación de un blog.</li>
        <li>En conclusión respecto a las bases de datos, son de gran utilidad al momento de agrupar y almacenar los datos, además que tenemos un acceso rápido a los datos aumentado así nuestra productividad</li>
    </ul>
    </td></tr>
</tbody>
</table>


<table>
<theader>
<tr><th>RETROALIMENTACIÓN GENERAL
    </th></tr>
</theader>
<tbody>
<tr><td>
    <pre>                                                                                          </pre>
    <pre>                                                                                          </pre>
    </td></tr>
</tbody>
</table>
</div>    
<p><b>REFERENCIAS Y BIBLIOGRAFÍA</b></p>
<ul>
    <li>https://www.w3schools.com/python/python_reference.asp</li>
    <li>https://docs.python.org/3/tutorial/</li>
    <li>https://www.youtube.com/watch?v=MAuHTqROt8w</li>
    <li>https://tutorial.djangogirls.org/es/django_start_project/</li>
    <li>https://docs.djangoproject.com/en/4.0/</li>
    <li>https://ellibrodepython.com/python-pep8</li>
</ul>
