import javax.swing.JOptionPane;

public class Matrix {
	String msg = "";
	int arow;
	int acol;

	private int[][] ticTacToe = { { 00, 01, 02 }, // row col 00, 01, 02
			{ 10, 11, 12 }, // row col 10, 11, 12
			{ 20, 21, 22 } // row col 20, 21, 22
	};

	private int[][] game = {

			{ 0, 0, 0 }, { 0, 1, 0 }, { 0, 0, 0 } };

	private char[][] realGame = {

			{ '-', '-', '-' }, { '-', '-', '-' }, { '-', '-', '-' } };

	// example
	String[][] checkers = new String[8][8];

	public void test2D() {

		// examples
		checkers[0][0] = "red";
		checkers[0][7] = "red king";
		checkers[3][4] = " ";
		checkers[7][0] = "black";
		checkers[7][7] = "black king";

		System.out.println("\nTest of 2D array\n");

		for (int row = 0; row < ticTacToe.length; row++) {
			for (int col = 0; col < ticTacToe[0].length; col++) {
				System.out.println("Test: ticTacToe[" + row + "][" + col + "} = " + ticTacToe[row][col]);
			}
			System.out.println();
		}

		System.out.println("\nPrint as 3 x 3\n");

		for (int row = 0; row < ticTacToe.length; row++) {
			for (int col = 0; col < ticTacToe[0].length; col++) {
				System.out.print(ticTacToe[row][col] + " ");
			}
			System.out.println();
		}
	}

	public void gameBoard() {
		for (int row = 0; row < game.length; row++) {
			for (int col = 0; col < game[0].length; col++) {
				System.out.println("Test: game[" + row + "][" + col + "} = " + game[row][col]);
			}
			System.out.println();
		}

		System.out.println("\nPrint as 3 x 3\n");

		for (int row = 0; row < game.length; row++) {
			for (int col = 0; col < game[0].length; col++) {
				System.out.print(game[row][col] + " ");
			}
			System.out.println("");
		}
		for (int row = 0; row < game.length; row++) {
			game[0][0] = 1;
			for (int col = 0; col < game[0].length; col++) {
				System.out.print(game[row][col] + " ");
			}
			System.out.println();
		}
		for (int row = 0; row < realGame.length; row++) {

			for (int col = 0; col < realGame[0].length; col++) {
				System.out.print(realGame[row][col] + " ");
			}
			System.out.println();
		}

	}

	public void realGame() {
		Boolean running = true;
		int runrum = 0;

		while (running == true) {
			runrum++;

			msg = "(first player) what is your move? (row)";
			arow = Integer.parseInt(JOptionPane.showInputDialog(null, msg));
			msg = "col?";
			acol = Integer.parseInt(JOptionPane.showInputDialog(null, msg));

			System.out.println("game start\n");

			for (int row = 0; row < realGame.length; row++) {

				for (int col = 0; col < realGame[0].length; col++) {
					System.out.print(realGame[row][col] + " ");
				}
				System.out.println();

			}

			System.out.println("first move(First player)\n");

			for (int row = 0; row < realGame.length; row++) {

				realGame[arow][acol] = 'X';

				for (int col = 0; col < realGame[0].length; col++) {
					System.out.print(realGame[row][col] + " ");
				}
				System.out.println();

			}

			if (realGame[0][0] == realGame[0][1] && realGame[0][1] == realGame[0][2] && realGame[0][0] == 'X'
					|| realGame[0][0] == realGame[0][1] && realGame[0][1] == realGame[0][2] && realGame[0][0] == 'O') {
				System.out.println("You Won!");
				running = false;
			} else if (realGame[1][0] == realGame[1][1] && realGame[1][1] == realGame[1][2] && realGame[1][0] == 'X'
					|| realGame[1][0] == realGame[1][1] && realGame[1][1] == realGame[1][2] && realGame[1][0] == 'O') {
				System.out.println("You Won!");
				running = false;
			} else if (realGame[2][0] == realGame[2][1] && realGame[2][1] == realGame[2][2] && realGame[2][0] == 'X'
					|| realGame[2][0] == realGame[2][1] && realGame[2][1] == realGame[2][2] && realGame[2][0] == 'O') {
				System.out.println("You Won!");
				running = false;
			} else if (realGame[0][0] == realGame[1][0] && realGame[1][0] == realGame[2][0] && realGame[0][0] == 'X'
					|| realGame[0][0] == realGame[1][0] && realGame[1][0] == realGame[2][0] && realGame[0][0] == 'O') {
				System.out.println("You Won!");
				running = false;
			} else if (realGame[0][1] == realGame[1][1] && realGame[1][1] == realGame[2][1] && realGame[0][1] == 'X'
					|| realGame[0][1] == realGame[1][1] && realGame[1][1] == realGame[2][1] && realGame[0][1] == 'O') {
				System.out.println("You Won!");
				running = false;
			} else if (realGame[0][2] == realGame[1][2] && realGame[0][2] == realGame[2][2] && realGame[0][2] == 'X'
					|| realGame[0][2] == realGame[1][2] && realGame[0][2] == realGame[2][2] && realGame[0][2] == 'O') {
				System.out.println("You Won!");
				running = false;
			} else if (realGame[0][0] == realGame[1][1] && realGame[0][0] == realGame[2][2] && realGame[0][0] == 'X'
					|| realGame[0][0] == realGame[1][1] && realGame[0][0] == realGame[2][2] && realGame[0][0] == 'O') {
				System.out.println("You Won!");
				running = false;
			} else if (realGame[0][2] == realGame[1][1] && realGame[0][2] == realGame[2][0] && realGame[0][2] == 'X'
					|| realGame[0][2] == realGame[1][1] && realGame[0][2] == realGame[2][0] && realGame[0][2] == 'O') {
				System.out.println("You Won!");
				running = false;
			} else if (runrum == 9) {
				System.out.println("It's a tie!");
				running = false;
			} else if (runrum < 9) {
				running = true;
			} else if (running == false) {
				System.exit(0);
			} else
				System.out.println("Good Job you broke everything.");

			if (running == false)
				System.exit(0);
			msg = "(Second Player) what is your move? (row)";
			arow = Integer.parseInt(JOptionPane.showInputDialog(null, msg));
			msg = "col?";
			acol = Integer.parseInt(JOptionPane.showInputDialog(null, msg));

			System.out.println("second move(Second player)\n");

			for (int row = 0; row < realGame.length; row++) {

				realGame[arow][acol] = 'O';

				for (int col = 0; col < realGame[0].length; col++) {
					System.out.print(realGame[row][col] + " ");
				}
				System.out.println();

			}
			if (realGame[0][0] == realGame[0][1] && realGame[0][1] == realGame[0][2] && realGame[0][0] == 'X'
					|| realGame[0][0] == realGame[0][1] && realGame[0][1] == realGame[0][2] && realGame[0][0] == 'O') {
				System.out.println("You Won!");
				running = false;
			} else if (realGame[1][0] == realGame[1][1] && realGame[1][1] == realGame[1][2] && realGame[1][0] == 'X'
					|| realGame[1][0] == realGame[1][1] && realGame[1][1] == realGame[1][2] && realGame[1][0] == 'O') {
				System.out.println("You Won!");
				running = false;
			} else if (realGame[2][0] == realGame[2][1] && realGame[2][1] == realGame[2][2] && realGame[2][0] == 'X'
					|| realGame[2][0] == realGame[2][1] && realGame[2][1] == realGame[2][2] && realGame[2][0] == 'O') {
				System.out.println("You Won!");
				running = false;
			} else if (realGame[0][0] == realGame[1][0] && realGame[1][0] == realGame[2][0] && realGame[0][0] == 'X'
					|| realGame[0][0] == realGame[1][0] && realGame[1][0] == realGame[2][0] && realGame[0][0] == 'O') {
				System.out.println("You Won!");
				running = false;
			} else if (realGame[0][1] == realGame[1][1] && realGame[1][1] == realGame[2][1] && realGame[0][1] == 'X'
					|| realGame[0][1] == realGame[1][1] && realGame[1][1] == realGame[2][1] && realGame[0][1] == 'O') {
				System.out.println("You Won!");
				running = false;
			} else if (realGame[0][2] == realGame[1][2] && realGame[0][2] == realGame[2][2] && realGame[0][2] == 'X'
					|| realGame[0][2] == realGame[1][2] && realGame[0][2] == realGame[2][2] && realGame[0][2] == 'O') {
				System.out.println("You Won!");
				running = false;
			} else if (realGame[0][0] == realGame[1][1] && realGame[0][0] == realGame[2][2] && realGame[0][0] == 'X'
					|| realGame[0][0] == realGame[1][1] && realGame[0][0] == realGame[2][2] && realGame[0][0] == 'O') {
				System.out.println("You Won!");
				running = false;
			} else if (realGame[0][2] == realGame[1][1] && realGame[0][2] == realGame[2][0] && realGame[0][2] == 'X'
					|| realGame[0][2] == realGame[1][1] && realGame[0][2] == realGame[2][0] && realGame[0][2] == 'O') {
				System.out.println("You Won!");
				running = false;
			} else if (runrum == 9) {
				System.out.println("It's a tie!");
				running = false;
			} else if (runrum < 9) {
				running = true;
			} else if (running == false) {
				System.exit(0);
			} else
				System.out.println("Good Job you broke everything.");

		}

	}

}// end of all

/*
 * 00 01 02 
 * 10 11 12 
 * 20 21 22
 */
