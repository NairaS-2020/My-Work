# My-Work
Search max, min, index (i'm junior)

using System;
namespace Function
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Please enter your length");
            int length = int.Parse(Console.ReadLine());
            int[] arr = GenArr(length);
            Print(arr);
            int min = GetMin(arr);
            Print1("Min is = ", min);
            int max = GetMax(arr);
            Print1("Max is = ", max);
            int max_Index = GetMaxIndex(arr);
            Print1("Max_Index is = ", max_Index);
            int min_Index = GetMinIndex(arr);
            Print1("Min_Index is = ", min_Index);
            int[] arr1 = Swap(arr, min, max, min_Index, max_Index);
            Console.ReadKey();
        }
        static int[] GenArr(int length)
        {
            int[] arr = new int[length];
            Random rnd = new Random();
            for (int i = 0; i < arr.Length; i++)
            {
                arr[i] = rnd.Next(1, 10);
            }
            return arr;
        }
        static int GetMin(int[] arr)
        {
            int min = arr[0];
            for (int i = 0; i < arr.Length; i++)
            {
                if (arr[i] < min)
                {
                    min = arr[i];
                }
            }
            return min;
        }
        static int GetMax(int[] arr)
        {
            int max = arr[0];
            for (int i = 0; i < arr.Length; i++)
            {
                if (arr[i] > max)
                {
                    max = arr[i];
                }
            }
            return max;
        }
        static int GetMinIndex(int[] arr)
        {
            int min = arr[0];
            int min_Index = 0;
            for (int i = 1; i < arr.Length; i++)
            {
                if (arr[i] < min)
                {
                    min = arr[i];
                    min_Index = i;
                }
            }
            return min_Index;
        }
        static int GetMaxIndex(int[] arr)
        {
            int max = arr[0];
            int max_Index = 0;
            for (int i = 1; i < arr.Length; i++)
            {
                if (arr[i] > max)
                {
                    max = arr[i];
                    max_Index = i;
                }

            }
            return max_Index;
        }
        static int[] Swap(int[] arr, int min, int max, int min_Index, int max_Index)
        {
            int temp = max;
            arr[max_Index] = min;
            arr[min_Index] = temp;
            return arr;
        }
        static void Print(int[] arr)
        {
            for (int i = 0; i < arr.Length; i++)
            {
                Console.WriteLine(arr[i]);
            }
        }
        static void Print1(string text, int a)
        {
            Console.WriteLine($"{text} {a}");
        }
    }
}