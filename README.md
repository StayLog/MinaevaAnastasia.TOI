# MinaevaAnastasia.TOI
using System; 
using System.Collections.Generic; 
using System.IO; 
using System.Linq; 
using System.Text; 
using System.Threading.Tasks; 

namespace TOIPERVOEZADANIE 
{ 
class Program 
{ 
static void Main(string[] args) 
{ 
byte[] arrfile = File.ReadAllBytes(@"C:\Users\anastasiaminaeva\Desktop\TOIDZ1.xls"); 

int[] work = new int [256]; 
for (int i = 0; i<arrfile.Length; i++) 
{ 
int count = arrfile[i]; 
work[count] += 1; 
} 
FileStream fs = new FileStream("dx.txt", FileMode.Create); 
StreamWriter r = new StreamWriter(fs); 

foreach (var b in work) 
{ 
r.WriteLine(b); 
} 
r.Close(); 
fs.Close(); 
Console.Read(); 
} 
} 
}
