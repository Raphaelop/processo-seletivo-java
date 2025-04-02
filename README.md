import java.util.ArrayList;
import java.util.List;

class Candidato {
    String nome;
    int experiencia; // Em anos
    
    public Candidato(String nome, int experiencia) {
        this.nome = nome;
        this.experiencia = experiencia;
    }
}

public class ProcessoSeletivo {
    public static void main(String[] args) {
        List<Candidato> candidatos = new ArrayList<>();
        candidatos.add(new Candidato("Ana", 5));
        candidatos.add(new Candidato("Bruno", 2));
        candidatos.add(new Candidato("Carlos", 4));
        candidatos.add(new Candidato("Daniela", 1));
        candidatos.add(new Candidato("Eduardo", 6));

        System.out.println("Analisando candidatos...");
        List<Candidato> selecionados = selecionarCandidatos(candidatos);
        
        System.out.println("Imprimindo lista de candidatos selecionados:");
        for (Candidato c : selecionados) {
            System.out.println("Selecionado: " + c.nome);
        }
        
        System.out.println("Fazendo ligações para os candidatos selecionados...");
        for (Candidato c : selecionados) {
            System.out.println("Ligando para " + c.nome + "...");
        }
    }

    public static List<Candidato> selecionarCandidatos(List<Candidato> candidatos) {
        List<Candidato> selecionados = new ArrayList<>();
        for (Candidato c : candidatos) {
            if (c.experiencia >= 3) { // Critério: pelo menos 3 anos de experiência
                selecionados.add(c);
            }
        }
        return selecionados;
    }
}
