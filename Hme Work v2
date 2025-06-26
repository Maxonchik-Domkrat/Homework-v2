using System;

namespace TextProcessorApp
{
    class TextProcessor
    {
        private string[] lines;
        private int vowelsCount;

        public TextProcessor(string[] inputLines)
        {
            lines = inputLines;
            vowelsCount = CountVowels();
        }

        public int this[int index]
        {
            get
            {
                if (index >= 0 && index < lines.Length)
                {
                    return lines[index].Length;
                }
                else
                {
                    throw new IndexOutOfRangeException("Невірний індекс рядка.");
                }
            }
        }

        public int VowelsCount
        {
            get { return vowelsCount; }
        }

        private int CountVowels()
        {
            int count = 0;
            string vowels = "aeiouаеєиіїоуюяAEIOUАЕЄИІЇОУЮЯ";

            foreach (string line in lines)
            {
                foreach (char c in line)
                {
                    if (vowels.Contains(c))
                        count++;
                }
            }

            return count;
        }
    }

    class Program
    {
        static void Main(string[] args)
        {
            string[] myText = {
                "Привіт, це перший рядок.",
                "А це другий.",
                "Голосні літери будуть рахуватись."
            };

            TextProcessor processor = new TextProcessor(myText);

            for (int i = 0; i < myText.Length; i++)
            {
                Console.WriteLine($"Довжина рядка {i}: {processor[i]} символів.");
            }

            Console.WriteLine($"\nЗагальна кількість голосних: {processor.VowelsCount}");
        }
    }
}
