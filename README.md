# ejemplosJava
Ejemplos con manejo de elementos en Java
package listasejemplos;

import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

public class ListasEjemplos {

    static Scanner sc = new Scanner(System.in);
    static List<String> ejemploListaString = new ArrayList<String>();

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        mostrar_desplegar_Menu();
    }

    public static void mostrar_desplegar_Menu() {
        int opcion = 0;
        do {
            System.out.println("");
            System.out.println("****************************");
            System.out.println("MANEJO DE LISTAS EN JAVA ");
            System.out.println("1. Pre-cargar lista.");
            System.out.println("2. Consultar tamaño de la lista.");
            System.out.println("3. Mostrar lista.");
            System.out.println("4. Mostrar elementos de la lista por separado.");
            System.out.println("5. Eliminar elemento de la lista.");
            System.out.println("6. Preguntar si la lista está vacía.");
            System.out.println("7. Buscar elemento en la lista.");
            System.out.println("8. Actualizar elemento de la lista");
            System.out.println("9. Borrar todos los elementos de la lista.");
            System.out.println("10. Salir");
            System.out.println("Seleccione una opción: ");

            opcion = sc.nextInt();
            if (ejemploListaString.isEmpty()) {
                switch (opcion) {
                    case 1:
                        precargarLista(ejemploListaString);
                        break;
                    case 9:
                        System.out.println("Gracias por utilizar nuestro sistema.");
                        System.exit(0);
                        break;
                    default:
                        System.out.println("Debe pre-cargar la lista primero antes de utilizar las demás opciones.");
                        break;
                }
            } else {
                switch (opcion) {
                    case 1:
                        precargarLista(ejemploListaString);
                        break;
                    case 2:
                        consultarTamanoLista(ejemploListaString);
                        break;
                    case 3:
                        mostrarLista(ejemploListaString);
                    case 4:
                        mostrarElementosLista(ejemploListaString);
                        break;
                    case 5:
                        System.out.println("Escriba el elemento a eliminar: ");
                        sc.nextLine();
                        String elementoEliminar = sc.nextLine();
                        eliminarElementoLista(elementoEliminar, ejemploListaString);
                        break;
                    case 6:
                        System.out.println(preguntarListaVacia(ejemploListaString));
                        break;
                    case 7:
                        System.out.println("Escriba el elemento a buscar: ");
                        sc.nextLine();
                        String elementoBuscar = sc.nextLine();
                        System.out.println(buscarElemento(elementoBuscar, ejemploListaString));
                        break;
                    case 8:
                        System.out.println("Escriba indice: ");
                        int indice = sc.nextInt();
                        System.out.println("Escriba el elemento a buscar: ");
                        sc.nextLine();
                        String elementoActualizado = sc.nextLine();
                        actualizarElementoLista(indice, elementoActualizado, ejemploListaString);
                    case 9:
                        limpiarLista(ejemploListaString);
                        break;
                    case 10:
                        System.out.println("Gracias por utilizar nuestro sistema.");
                        System.exit(0);
                        break;
                }
            }
        } while (opcion != 10);
    }

    public static void precargarLista(List lista) {
        lista.add("Pepe");
        lista.add("Rosa");
        lista.add("Luis");
        System.out.println("La lista se ha precargado correctamente");
    }

    public static void consultarTamanoLista(List lista) {
        System.out.println("El tamaño de la lista es: " + lista.size()); //size recupera el tamaño de la lista
    }

    public static void mostrarLista(List lista) {
        System.out.println("LISTA List");
        System.out.println("Contenido lista: " + lista); //imprime la lista como un vector
    }

    public static void mostrarElementosLista(List lista) {
        System.out.println("Elementos de cada lista de forma individual: ");
        for (int i = 0; i < lista.size(); i++) {
            System.out.println("Elemento en la posicion " + i + " -> " + lista.get(i));
        }
    }

    public static void eliminarElementoLista(String elemento, List lista) {
        System.out.println(buscarElemento(elemento, lista));
        if (lista.remove(elemento)) {//remove(i) elmina el elemento de la posición i
            System.out.println("El elemento " + elemento + " fué eliminado de la lista.");
        } else {
            System.out.println("El elemento " + elemento + " no existe en la lista.");
        }

    }

    public static String preguntarListaVacia(List lista) {
        System.out.println("¿Está la lista vacía?");
        String mensaje = "";
        if (lista.isEmpty()) {
            mensaje = "Lista vacía";
        } else {
            mensaje = "No. La lista contiene: " + lista.size() + " elementos.";
        }
        return mensaje;
    }

    public static String buscarElemento(String elemento, List lista) {
        System.out.println("¿La lista contiene a " + elemento + "?");
        String mensaje = "";
        if (lista.contains(elemento)) {
            mensaje = elemento + " SÍ está en la lista.";
        } else {
            mensaje = elemento + " NO está en la lista.";
        }
        return mensaje;
    }

    public static void actualizarElementoLista(int indice, String elemento, List lista) {

    }

    public static void limpiarLista(List lista) {
        lista.clear();
        System.out.println("La lista ahora está vacia. Es decir que contiene: " + lista.size() + " elementos.");
    }

}
