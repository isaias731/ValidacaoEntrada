import java.util.InputMismatchException;
import java.util.Scanner;

public class ValidacaoEntrada {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int numero = 0;
        boolean entradaValida = false;

        do {
            try {
                System.out.print("Digite um número entre 1 e 10: ");
                numero = scanner.nextInt();

                if (numero >= 1 && numero <= 10) {
                    entradaValida = true;
                } else {
                    System.out.println("Número fora do intervalo. Tente novamente.");
                }
            } catch (InputMismatchException e) {
                System.out.println("Entrada inválida. Por favor, digite um número inteiro.");
                scanner.nextLine(); // Limpa o buffer do scanner
            }
        } while (!entradaValida);

        System.out.println("Número válido: " + numero);
        scanner.close();
    }
}
