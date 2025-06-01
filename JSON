using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Text.Json;
using System.Text.Json.Serialization;
using System.IO;
namespace librito
{
    public class Person
    {
        [JsonPropertyName("firstname")]

        public string FirstName { get; set; }

        [JsonPropertyName("lastname")]
        public string LastName { get; set; }

        [JsonPropertyName("age")]
        public int Age { get; set; }

    }
    internal class Program
    {
        static void Main(string[] args)
        {
            string filePath = @"C:\Users\miamo\source\repos\librito\librito\bin\Debug\uwu.json";
            string jsonString = "";
            try
            {
                jsonString = File.ReadAllText(filePath);
            }
            catch (FileNotFoundException)
            {
                Console.WriteLine($"El archivo {filePath} no se encontró.");
                return;
            }
            catch (Exception ex)
            {
                Console.WriteLine($"Error al leer el archivo: {ex.Message}");
                return;
            }
            try
            {
                Person person = JsonSerializer.Deserialize<Person>(jsonString);
                //3. imprimir los valores del objeto
                Console.WriteLine($"Nombre: {person.FirstName}");
                Console.WriteLine($"Apellido: {person.LastName}");
                Console.WriteLine($"Edad: {person.Age}");
                Console.ReadKey();
            }
            catch (JsonException ex)
            {
                Console.WriteLine($"Error al deserializar el JSON: {ex.Message}");
            }
            catch (Exception ex)
            {
                Console.WriteLine($"Error inesperado: {ex.Message}");
            }
            

        }
    }
}
