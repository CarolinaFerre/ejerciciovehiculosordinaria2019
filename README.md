# ejerciciovehiculosordinaria2019
ejercicio de objetos, ejercicio 3 del examen de la ordinaria de 2019

Codificar una clase denominada Vehículo donde queremos almacenar los atributos privados:  matrícula (String) y  número de veces que se ha prestado, y si el estado actual del vehículo es  prestado o disponible. La clase tendrá además un constructor, que recibe como único parámetro la matricula, y los métodos públicos boolean alquilar(), void devolver() y String toString().  Si está prestado no se puede volver a prestar. El método toString devolverá la cadena con la matrícula, si esta prestado o no y el número de veces que se ha prestado. ¿Si queremos  almacenar esta clase en un HashMap como deberíamos definir esta colección, pon un ejemplo de declaración? ¿Si queremos poder utilizar el método sort de la clase Collections o Arrays que deberíamos incluir en la clase Vehículo?

public class Vehiculo implements Comparable<Vehiculo>
{
    
    private String matricula;
    private int nprestamos;
    private boolean estaPrestado;      
        
    public Vehiculo(String matricula)
    {
        this.matricula = matricula;
        nprestamos = 0;
        estaPrestado = false;
    }

    public boolean alquilar (){
        if ( !estaPrestado ){
            estaPrestado = true;
            nprestamos++;
            return true;
        }
        return false;
    }
    
    public void devolver(){
        estaPrestado = false;
    }
    
    public String toString (){
        String resu = matricula+": ";
         resu+= (estaPrestado)?"PRESTADO  ":"DISPONIBLE";
         resu+= " : Nº de prestamos "+nprestamos;
         return resu;
        }
    
    // IMPLEMENTA COMPARABLE PARA PODER ORDENAR
    public int compareTo ( Vehiculo otro ){
        return matricula.compareTo(otro.matricula);
    }
}       
    
Definir un hashMap
HashMap <String,Vehiculo > map;
Debemos implementar el interfaz comparable.
