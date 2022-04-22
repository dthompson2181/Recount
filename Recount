/* Group 11: Recount Kattis Problem
 * Names: Jason Wang, Allyson Windell, Dequandre Span, Kayla Worrell, and Daniel Thompson
 * Date: 04/24/2022
 * Description: This app is used as a polling system and allows the user to input a list of names
 * in order to find out whose name was repeated the most. It will also let the user know when there is
 * an equal number of votes amongst more than one candidate indicating that there is a tie.
 */
using System;
using System.Collections.Generic;

namespace KattisRecountGroup11
{
    class Program
    {
        static void Main(string[] args)
        {
            IDictionary<string, int> candidates = new Dictionary<string, int>();
            string name;
            int x, maxCount = 0, countOfMaxCount = 0;
            string maxName = "Candidate1";
            int count = 0;

            do
            {
                // Establish the name to be equal to the input that is in each line
                name = Console.ReadLine();
                //loop will continue until user inputs "***"
                if (name == "***")
                    break;
                if (name.Trim().Equals(""))
                    continue;

                for (x = 0; x < name.Length; x++)
                    // Establishing valid character inputs
                    if (name[x] != '-' && name[x] != ' ' && Char.IsLetterOrDigit(name, x) == false)
                        break;

                // Displays "Invalid name" if user inputs characters that were deemed invalid from above
                if (x != name.Length)
                {
                    Console.WriteLine("Invalid name");
                    continue;
                }
                count++;
                // To determine whose name was inputed the most
                if (candidates.ContainsKey(name))
                {
                    candidates[name] += 1;

                    if (candidates[name] > maxCount)
                    {
                        maxName = name;
                        maxCount = candidates[name];
                        countOfMaxCount = 1;
                    }
                    else if (candidates[name] == maxCount)
                        countOfMaxCount += 1;
                }
                else 
                {
                    if (maxCount == 0)
                    {
                        maxName = name;
                        maxCount = 1;
                        countOfMaxCount = 1;
                    }
                    // Using the Add() method to add a key/value
                    candidates.Add(name, 1);
                    if (maxCount == 1)
                        countOfMaxCount += 1;

                }
            } while (name != "***");

            // If there is a tie between candidates display "Runoff!"
            if (count <= 1 || countOfMaxCount > 1)
                Console.WriteLine("Runoff!");
            else
            // Candidate with most votes is displayed
                Console.WriteLine(maxName);
           

        }
    }
}
