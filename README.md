# 202310702
Ammar abuhusain 202310702


using System;

class Program
{
    static void Main()
    {
        
          
            Console.Write("Enter the minimum number: ");
            int min = int.Parse(Console.ReadLine());
            Console.Write("Enter the maximum number: ");
            int max = int.Parse(Console.ReadLine());
            if (min > max)
            {
                Console.WriteLine("Error: The minimum number should be less than or equal to the maximum number.");
                return;
            }
            int range = max - min + 1;
            int[] frequencyArray = new int[range];
            Random ran = new Random();
            
            for (int i = 0; i < 1000; i++)
            {
                int RandomNum = ran.Next(min, max + 1);
                int Storage = RandomNum - min;
                frequencyArray[Storage]++;
            }
            int[,] resultArray = new int[range, 2];
            for (int i = 0; i < range; i++)
            {
                resultArray[i, 0] = min + i;
                resultArray[i, 1] = frequencyArray[i];
            }
            Console.WriteLine("Number\tFrequency");
            for (int i = 0; i < range; i++)
            {
                Console.WriteLine($"{resultArray[i, 0]}\t{resultArray[i, 1]}");
            }
        }
        catch (IndexOutOfRangeException ex)
        {
            Console.WriteLine("Error: Array index out of bounds. Details: " + ex.Message);
        }
        catch (FormatException ex)
        {
            Console.WriteLine("Error: Invalid input. Please enter a valid integer. Details: " + ex.Message);
        }
        catch (Exception ex)
        {
            Console.WriteLine("An unexpected error occurred: " + ex.Message);
        }
        Console.WriteLine("Press Enter to exit...");
        Console.ReadLine();

        Console.WriteLine("press enter when done");
        Console.ReadLine();
    }
}
