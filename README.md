class Funcionario {
  double salarioBase;
  double horasExtras;
  double horasFaltas;

  Funcionario(this.salarioBase, this.horasExtras, this.horasFaltas);

  double get valorHora => salarioBase / (30 * 8);

  double get valorHoraExtra => valorHora * 1.5;

  double get totalHorasExtras => horasExtras * valorHoraExtra;

  double get totalHorasFaltas => horasFaltas * valorHora;

  double get salarioFinal => salarioBase + totalHorasExtras - totalHorasFaltas;
}

void main() {

  double salario = 3000.0; 
  double horasExtras = 10.0; 
  double horasFaltas = 5.0; 

  var funcionario = Funcionario(salario, horasExtras, horasFaltas);

  print("\n--- Resumo do Salário ---");
  print("Salário Base: R\$ ${funcionario.salarioBase.toStringAsFixed(2)}");
  print("Valor da Hora: R\$ ${funcionario.valorHora.toStringAsFixed(2)}");
  print("Valor da Hora Extra: R\$ ${funcionario.valorHoraExtra.toStringAsFixed(2)}");
  print("Total Recebido por Horas Extras: R\$ ${funcionario.totalHorasExtras.toStringAsFixed(2)}");
  print("Total Descontado por Faltas: R\$ ${funcionario.totalHorasFaltas.toStringAsFixed(2)}");
  print("Salário Final: R\$ ${funcionario.salarioFinal.toStringAsFixed(2)}");
}
