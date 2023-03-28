# QUIZ


import java.util.Scanner;

public class Quiz {
    public static void main(String[] args) {
        
        Scanner scanner = new Scanner(System.in);
        int resposta;
        
        System.out.println("Bem-vindo ao Quiz!");
        
        do {
            System.out.println("\nEscolha uma opção:");
            System.out.println("1. Iniciar Quiz");
            System.out.println("2. Sair");
            resposta = scanner.nextInt();
            
            switch (resposta) {
                case 1:
                    int pontuacaoTotal = iniciaQuiz(scanner);
                    System.out.println("\nFim do Quiz! Pontuação: " + pontuacaoTotal);
                    break;
                case 2:
                    System.out.println("Obrigado por jogar!");
                    break;
                default:
                    System.out.println("Opção inválida!");
                    break;
            }
        } while (resposta != 2);
        
        scanner.close();
    }
    
    public static int iniciaQuiz(Scanner scanner) {
        int pontuacaoTotal = 0;
        
        pontuacaoTotal += perguntaCapitalBrasil(scanner);
        pontuacaoTotal += perguntaDescobrimentoBrasil(scanner);
        pontuacaoTotal += perguntaMonaLisa(scanner);
        
        return pontuacaoTotal;
    }
    
    public static int perguntaCapitalBrasil(Scanner scanner) {
        System.out.println("\nQual é a capital do Brasil?");
        String respostaUsuario = scanner.nextLine();
        
        if (respostaUsuario.equalsIgnoreCase("Brasília")) {
            System.out.println("Resposta correta!");
            return 1;
        } else {
            System.out.println("Resposta incorreta!");
            return 0;
        }
    }
    
    public static int perguntaDescobrimentoBrasil(Scanner scanner) {
        System.out.println("\nQuem descobriu o Brasil?");
        String respostaUsuario = scanner.nextLine();
        
        if (respostaUsuario.equalsIgnoreCase("Pedro Álvares Cabral")) {
            System.out.println("Resposta correta!");
            return 1;
        } else {
            System.out.println("Resposta incorreta!");
            return 0;
        }
    }
    
    public static int perguntaMonaLisa(Scanner scanner) {
        System.out.println("\nQuem pintou a Mona Lisa?");
        String respostaUsuario = scanner.nextLine();
        
        if (respostaUsuario.equalsIgnoreCase("Leonardo da Vinci")) {
            System.out.println("Resposta correta!");
            return 1;
        } else {
            System.out.println("Resposta incorreta!");
            return 0;
        }
    }
}
