# CreateFile.net<br>
using System;<br>
using System.IO;<br>
namespace Exercise<br>
{<br>
    class FileRead<br>
    {<br>
       public static void Main()<br>
        {<br>
            string fileName;<br>
            while(true)<br>
            {<br>
                Console.WriteLine("\n.......MENU......\n");<br>
                Console.WriteLine("\n1.Create a File");<br>
                Console.WriteLine("\n2.Existence of the File");<br>
                Console.WriteLine("\n3.Read the contents of the File");<br>
                Console.WriteLine("\n4.Exit");<br>
                Console.WriteLine("\nEnter your choice:");<br>
                int ch = int.Parse(Console.ReadLine());<br>
                switch(ch)<br>
                {<br>
                    case 1:<br>
                        Console.Write("\nEnter the file name to create:");<br>
                        fileName = Console.ReadLine();<br>
                        Console.WriteLine("\nWrite the Contents to the File:\n");<br>
                        string r = Console.ReadLine();<br>
                        using (StreamWriter fileStr=File.CreateText(fileName))<br>
                        {<br>
                            fileStr.WriteLine(r);<br>
<br>
                        }<br>
                        Console.WriteLine("File is Created...");<br>
                        break;<br>
                    case 2:<br>
                        Console.Write("\nEnter the file name:");<br>
                        fileName = Console.ReadLine();<br>
                        if(File.Exists(fileName))<br>
                        {<br>
                            Console.WriteLine("File exits...");<br>
                        }<br>
                        else<br>
                        {<br>
                            Console.WriteLine("File does not exits in the current directory!");<br>
                        }<br>
                        break;<br>
                    case 3:<br>
                        Console.Write("Enter the file name to read the contents:\n");<br>
                        fileName = Console.ReadLine();<br>
                        if (File.Exists(fileName))<br>
                        {<br>
                            using (StreamReader sr = File.OpenText(fileName))<br>
                            {<br>
                                string s = "";<br>
                                Console.WriteLine(" Here is the content of the file : ");<br>
                                while ((s = sr.ReadLine()) != null)<br>
                                {<br>
                                    Console.WriteLine(s);<br>
                                }<br>
                                Console.WriteLine("");<br>
                            }<br>
                        }<br>
                        else<br>
                        {<br>
                            Console.WriteLine("File does not exists");<br>
                        }<br>
                        break;<br>
                    case 4:<br>
                        Console.WriteLine("\n Exiting...");<br>
                        return;<br>
                    default:<br>
                        Console.WriteLine("\n Invalid choice");<br>
                        break;<br>
                }<br>
            }<br>
        }<br>
    }<br>
}<br>

OUTPUT:-
<br>
![Screenshot 2022-02-17 052851](https://user-images.githubusercontent.com/98145032/154411821-76583392-d45a-4e1c-aef0-004792060422.png)
<br>
![Screenshot 2022-02-17 053022](https://user-images.githubusercontent.com/98145032/154411840-e3e3075e-8388-4054-b93f-d97d200405ab.png)
<br>
![Screenshot 2022-02-17 053116](https://user-images.githubusercontent.com/98145032/154411882-d85b3e6b-732c-46e5-aa86-a92b72835d8b.png)
