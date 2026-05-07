using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Globalization;

namespace vitor
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Funcionario Func = new Funcionario();

            Console.Write("Nome: ");
            Func.Nome = Console.ReadLine();
            Console.Write("Salario Bruto: ");
            Func.SalarioBruto = double.Parse(Console.ReadLine(), CultureInfo.InvariantCulture);
            Console.Write("Imposto: ");
            Func.Imposto = double.Parse(Console.ReadLine(), CultureInfo.InvariantCulture);

            Console.WriteLine("Funcionario: " + Func);

            Console.Write("Digite a porcentagem para aumentar o salrio: ");
            double porcent = double.Parse(Console.ReadLine(), CultureInfo.InvariantCulture);
            Func.AumentoSalario(porcent);

                Console.WriteLine("Dados atualizados: " + Func);
        }
    }
}




using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Globalization;

namespace vitor
{
    internal class Funcionario
    {
        public string Nome;
        public double SalarioBruto;
        public double Imposto;

        public double SalarioLiquido()
        {
            return SalarioBruto - Imposto;
        }
        public void AumentoSalario(double porcentagem)
        {
            SalarioBruto = SalarioBruto + (SalarioBruto * porcentagem / 100);
        }
        public override string ToString()
        {
            return Nome
                + ", R$ "
                + SalarioLiquido().ToString("F2", CultureInfo.InvariantCulture);
        }
    }
}









