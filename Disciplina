import java.util.ArrayList;

public class Disciplina {
    public String nome;
    public int carga;
    private Professor professor;
    public ArrayList<Aluno> alunos;

    public Disciplina(String nome, int carga, Professor professor){
        this.nome = nome;
        this.carga = carga;
        this.professor = professor;
        this.alunos = new ArrayList<>();  // Inicializando a lista de alunos
    }

    public String getNome(){
        return nome;
    }
    public void setNome(String nome){
        this.nome = nome;
    }

    public void adicionarAluno(Aluno aluno) {
        alunos.add(aluno);
    }

    public void removerAluno(Aluno aluno) {
        alunos.remove(aluno);
    }

    public ArrayList<Aluno> getAlunos() {
        return alunos;
    }

    public ArrayList<String> getAlunosNomes() {
        ArrayList<String> nomes = new ArrayList<>();
        for (Aluno aluno : alunos) {
            nomes.add(aluno.getNome());
        }
        return nomes;
    }

    public Professor getProfessor() {
        return professor;
    }

    public void setProfessor(Professor professor) {
        this.professor = professor;
    }

    @Override
    public String toString(){
        return "Disciplina: " + nome + "\nCarga horária: " + carga + "\nProfessor: " + professor.getNome() + "\nAlunos: " + getAlunosNomes();
    }
}
