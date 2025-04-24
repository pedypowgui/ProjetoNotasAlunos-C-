using System;
using System.Collections.Generic;

namespace ProjetoNotasAlunos{
	class Program{
		static void Main() {
			//Verificação para adicionar ou não outro aluno através do loop
			string opc = " ";
			bool AdicionarAluno = true;
			
			List<string> alunos = new List<string>();
			List<float> medias = new List<float>();
			List<char> notaLetra = new List<char>();
			
			while (AdicionarAluno) {	
				Console.Write("\nQuer Adicionar um aluno e calcular sua média?<s/n>");
				
				//Em caso de caractere nulo
				opc = Console.ReadLine()!.ToLower();
				
				//Caso queira adicionar um aluno
				if (opc == "s") {
					float somaNotas = 0;
					float mediaAlunoAtual = 0;
					char notaLetraAtual;
					string nomeAluno;
					
					Console.Write("\nNome do aluno:");
					
					//Receber nome do aluno
					nomeAluno = Console.ReadLine();
					alunos.Add(nomeAluno);
					
					//Receber as 5 notas do aluno
					for (int i = 0; i < 5; i++) {
						Console.Write($"Nota {i+1}: ");	
						float nota = float.Parse(Console.ReadLine()!);
						if (nota > 10 || nota < 0) {
							Console.WriteLine("ERRO: Digite apenas notas de 0 a 10");
							i -= 1;
						} else {
							somaNotas += nota;
						}
					}
					
					//Calculo da média do aluno
					mediaAlunoAtual = somaNotas/5;
					medias.Add(mediaAlunoAtual);
					
					//Atribuir nota em letra do aluno
					if (mediaAlunoAtual >= 9 && mediaAlunoAtual <= 10) {
						notaLetraAtual = 'A';
					} else if (mediaAlunoAtual >= 7 && mediaAlunoAtual < 9) {
						notaLetraAtual = 'B';
					} else if (mediaAlunoAtual >= 6 && mediaAlunoAtual < 7) {
						notaLetraAtual = 'C';
					} else if (mediaAlunoAtual >= 5 && mediaAlunoAtual < 6) {
						notaLetraAtual = 'D';
					} else {
						notaLetraAtual = 'F';
					}
					
					notaLetra.Add(notaLetraAtual);
					
					//Imprimir dados do aluno atual
					Console.WriteLine($"ALUNO            | MEDIA - NOTA");
					Console.WriteLine($"{nomeAluno,-16} | {mediaAlunoAtual:F2} - {notaLetraAtual}");
			
				} else if (opc == "n") {
					AdicionarAluno = false;
					
					Console.WriteLine("\n=== RESUMO DA TURMA COMPLETA ===\n");
					Console.WriteLine($"ALUNO            | MEDIA - NOTA");
					Console.WriteLine($"---------------- | ------------");
					
					for (int i = 0; i < alunos.Count; i++) {
						Console.WriteLine($"{alunos[i],-16} | {medias[i]:F2} - {notaLetra[i]}");
					}
					
				} else {
					Console.WriteLine("ERRO: Valor inválido");
				}
			}
			
		}
	}
}
