# sesion_04_lab02
Laboratorio de variables

# Enunciado del Ejercicio

*NOTA: Siempre que se use una variable declarada, la deberemos de integrar en el playbook

- Crearemos u repositorio en GitHub con el nombre sesion_04_lab02
- Lo clonaremos en nuestro equipos
- Insertaremos el inventario y el ansible.cfg necesario para conectarnos a los nodos
- Crearemos un directorio vars dentro del proyecto el cual contendrá las variables externas en el archivo default.yml
- Dentro del archivo default.yml declararemos una Lista de servicios y una estructura Arrays de diccionarios con el siguiente formato:
		servicios:
		  - sshd
		  - firewalld
		  - httpd
		  - mariadb

		usuarios:
		  administrador:
			grupo: root
			generar_key: yes
			ruta_key: .ssh/id_rsa
			expira: -1
		  everis_pruebas:
			grupo: everis
			generar_key: no
			uid: 1212
			expira: 12407987
		  nuestro:
		    grupo: ctic, devops
			generar_key: yes
			ruta_key: .ssh/id_rsa
			expira: 122403387		

- Creamos un playbook con el nombre "playbook.yml"
- Titularemos el playbook "Laboratorio de Variables"
- Crearemos las siguientes tareas para que ataquen a ambos nodos:
	- Instalaremos los servicios declarados en el archivo de variables
	- Arrancaremos estos servicios (habilitando el arranque con el inicio del equipo)
	- Crearemos los siguientes grupos de Sistema (estos grupos deben de ser declarados como variable dentro del playbook):
		- ctic
		- devops
		- everis
	
	- Crearemos los usuarios de la lista de variables externas
	- Reiniciaremos los servicios
	- Reiniciaremos los nodos
