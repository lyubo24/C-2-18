using System;
using System.Collections.Generic;
using System.Linq;


namespace _18.RemoveAndSortTheMinNumber
{
    class Program
    {
        static void Main(string[] args)
        {
            //* Write a program that reads an array of integers and removes from it a minimal number of elements in such way that the remaining array is sorted in increasing order. 
            //Print the remaining sorted array. Example: {6, 1, 4, 3, 0, 3, 6, 4, 5}  {1, 3, 3, 4, 5}

            //List<int> arr = new List<int>() { 0, 6, 1, 4, 3, 0, 3, 6, 4, 5 };
            List<int> arr = new List<int>() { 6, 1, 4, 3, 0, 3, 6, 4, 5 };


            //Console.Write("Please enter the size of the array: ");
            //int size = int.Parse(Console.ReadLine());
            //List<int> arr = new List<int>();

            //for (int i = 0; i < size; i++)
            //{
            //    Console.Write("Please enter the value {0}:", i + 1);
            //    arr.Add(int.Parse(Console.ReadLine()));
            //}


            SortAndReturn(arr);

            Console.WriteLine();
        }

        static void SortAndReturn(List<int> arr)
        {
            List<int> newArr = new List<int>(arr);
            int count = 0;

            for (int i = 0; i < newArr.Count - 1; i++)
            {
                if (newArr[i + 1] < 1)
                {
                    newArr.RemoveAt(i + 1);
                    i = -1;
                    count++;
                }
                else if ((newArr[i] > newArr[i + 1]) || newArr[i] < 1)
                {
                    newArr.RemoveAt(i);
                    i--;
                    count++;
                }
            }
            Console.WriteLine("Result: " + string.Join(", ", newArr));
        }

    }
}
