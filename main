import java.util.ArrayList;
import java.util.Collections;
import java.util.Scanner;

public class Main {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int option = 0;
        ArrayList<Disciplina> lista_disciplinas = new ArrayList<>();
        ArrayList<Aluno> lista_alunos = new ArrayList<>();

        Professor professor1 = new Professor("Bob", 4500, "Matemática");
        Professor professor2 = new Professor("Luana", 4500, "Biologia");
        Professor professor3 = new Professor("Gabriel", 4500, "Física");
        Professor professor4 = new Professor("Maria", 4500, "Química");
        Professor professor5 = new Professor("Mateus", 4500, "História");

        Disciplina matematica = new Disciplina("Matemática", 120, professor1);
        Disciplina biologia = new Disciplina("Biologia", 120, professor2);
        Disciplina fisica = new Disciplina("Física", 120, professor3);
        Disciplina quimica = new Disciplina("Química", 120, professor4);
        Disciplina historia = new Disciplina("História", 120, professor5);
        Collections.addAll(lista_disciplinas, matematica, biologia, fisica, quimica, historia);

        Aluno aluno1 = new Aluno(123, "João", 19);
        Aluno aluno2 = new Aluno(124, "Rafa", 20);
        Aluno aluno3 = new Aluno(125, "Pedro", 21);
        Aluno aluno4 = new Aluno(126, "Ana", 22);
        Collections.addAll(matematica.alunos, aluno1, aluno2, aluno3, aluno4);
        Collections.addAll(biologia.alunos, aluno1, aluno2, aluno4);
        Collections.addAll(fisica.alunos, aluno1, aluno2, aluno3);
        Collections.addAll(quimica.alunos, aluno1, aluno3, aluno4);
        Collections.addAll(historia.alunos, aluno1, aluno2, aluno3, aluno4);

        Collections.addAll(lista_alunos, aluno1, aluno2, aluno3, aluno4);
        Collections.addAll(aluno1.disciplinas, matematica.nome, biologia.nome, fisica.nome, quimica.nome, historia.nome);
        Collections.addAll(aluno2.disciplinas, matematica.nome, biologia.nome, fisica.nome, historia.nome);
        Collections.addAll(aluno3.disciplinas, matematica.nome, fisica.nome, quimica.nome, historia.nome);
        Collections.addAll(aluno4.disciplinas, matematica.nome, biologia.nome, quimica.nome, historia.nome);

        boolean loop = true;
        System.out.println("Bem vindo ao sistema de turmas!");
        while (loop) {
            System.out.println("Agora, o que deseja fazer?\n1 - Matricular um aluno\n2 - Listar alunos de uma disciplina\n3 - Mostrar informações de uma disciplina\n4 - Listar disciplinas\n5 - Mostrar informações do aluno por matrícula\n6 - Alterar informações de um aluno\n0 - Sair\n");
            option = sc.nextInt();
            sc.nextLine();

            switch (option) {
                case 1:
                    System.out.println("Digite o nome do aluno a ser cadastrado: ");
                    String nomeAluno = sc.nextLine();

                    System.out.println("Digite a matrícula do aluno:");
                    int matriculaAluno = sc.nextInt();

                    System.out.println("Digite a idade do aluno:");
                    int idadeAluno = sc.nextInt();
                    sc.nextLine(); // Consumir o newline

                    // Criar o novo aluno
                    Aluno novoAluno = new Aluno(matriculaAluno, nomeAluno, idadeAluno);

                    System.out.println("Escolha as disciplinas para matricular o aluno (digite os números separados por vírgula):");
                    for (int i = 0; i < lista_disciplinas.size(); i++) {
                        System.out.println((i + 1) + " - " + lista_disciplinas.get(i).getNome());
                    }

                    String disciplinasEscolhidas = sc.nextLine();
                    String[] disciplinasArray = disciplinasEscolhidas.split(",");

                    for (String disciplinaIndice : disciplinasArray) {
                        int indice = Integer.parseInt(disciplinaIndice.trim()) - 1;
                        Disciplina disciplinaSelecionada = lista_disciplinas.get(indice);
                        novoAluno.disciplinas.add(disciplinaSelecionada.getNome());
                        disciplinaSelecionada.alunos.add(novoAluno);
                    }

                    lista_alunos.add(novoAluno);
                    System.out.println("Aluno matriculado com sucesso!");

                    break;

                case 2:
                    System.out.println("Escolha a disciplina para listar os alunos: ");
                    for (int i = 0; i < lista_disciplinas.size(); i++) {
                        System.out.println((i + 1) + " - " + lista_disciplinas.get(i).getNome() + "\n");
                    }
                    int escolha = sc.nextInt();
                    System.out.println("Alunos: " + lista_disciplinas.get(escolha - 1).getAlunosNomes());
                    break;

                case 3:
                    System.out.println("Escolha a disciplina para mostrar as informações:\n");
                    for (int i = 0; i < lista_disciplinas.size(); i++) {
                        System.out.println((i + 1) + " - " + lista_disciplinas.get(i).getNome() + "\n");
                    }
                    int escolha2 = sc.nextInt();
                    System.out.println(lista_disciplinas.get(escolha2 - 1).toString());
                    break;

                case 4:
                    System.out.println("Disciplinas: ");
                    for (int i = 0; i < lista_disciplinas.size(); i++) {
                        System.out.println((i + 1) + " - " + lista_disciplinas.get(i).getNome() + "\n");
                    }
                    break;

                case 5:
                    System.out.println("Digite a matrícula do aluno: (123, 124, 125, 126 --> números pra vc não ter que prcurar no código prof kkkk)");
                    int matricula = sc.nextInt();
                    boolean encontrou = false;
                    for (int i = 0; i < lista_alunos.size(); i++) {
                        if (lista_alunos.get(i).getMatricula() == matricula) {
                            System.out.println("Aluno: " + matricula + "\nNome: " + lista_alunos.get(i).getNome() + "\nIdade: " + lista_alunos.get(i).getIdade() + "\nDisciplinas matriculadas: " + lista_alunos.get(i).getDisciplinas());
                            encontrou = true;
                            break;
                        }
                    }
                    if (!encontrou) {
                        System.out.println("Aluno não encontrado");
                    }
                    break;

                case 6:
                    System.out.println("Digite o nome do aluno que deseja alterar:");
                    for (int i = 0; i < lista_alunos.size(); i++) {
                        System.out.println(lista_alunos.get(i).getNome());
                    }
                    String nomex = sc.nextLine();
                    Aluno alunoAlterar = null;
                    for (Aluno alunoObj : lista_alunos) {
                        if (alunoObj.getNome().equalsIgnoreCase(nomex)) {
                            alunoAlterar = alunoObj;
                            break;
                        }
                    }
                    if (alunoAlterar == null) {
                        System.out.println("Aluno não encontrado.");
                        break;
                    }

                    System.out.println("O que deseja alterar no aluno?\n1 - Nome\n2 - Idade\n3 - Disciplinas");
                    int escolha3 = sc.nextInt();
                    sc.nextLine();  // Consumir o newline

                    switch (escolha3) {
                        case 1:
                            System.out.println("Digite o novo nome: ");
                            String nome = sc.nextLine();
                            alunoAlterar.setNome(nome);
                            System.out.println("Nome alterado com sucesso!");
                            break;

                        case 2:
                            System.out.println("Digite a nova idade: ");
                            int idade = sc.nextInt();
                            alunoAlterar.setIdade(idade);
                            System.out.println("Idade alterada com sucesso!");
                            break;

                        case 3:
                            System.out.println("Disciplinas atuais do aluno:");
                            for (int j = 0; j < alunoAlterar.getDisciplinas().size(); j++) {
                                System.out.println((j + 1) + " - " + alunoAlterar.getDisciplinas().get(j));
                            }

                            System.out.println("Digite o nome da disciplina para adicionar/remover:");
                            String disciplina = sc.nextLine();

                            if (alunoAlterar.getDisciplinas().contains(disciplina)) {
                                alunoAlterar.getDisciplinas().remove(disciplina);
                                System.out.println("Disciplina removida com sucesso!");
                            } else {
                                alunoAlterar.getDisciplinas().add(disciplina);
                                System.out.println("Disciplina adicionada com sucesso!");
                            }
                            break;

                        default:
                            System.out.println("Opção inválida!");
                            break;
                    }
                    break;

                case 0:
                    System.out.println("Saindo do sistema...");
                    loop = false;  // Termina o loop
                    break;

                default:
                    System.out.println("Opção inválida!");
                    break;
            }
        }
        sc.close();  // Fecha o scanner após sair do loop
    }
}
