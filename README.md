Download Link: https://assignmentchef.com/product/solved-cop3275-programming-using-c-programming-assignment-3
<br>
<ol>

 <li>You have to upload your codes in both Canvas and the Judge system at <a href="https://cop3275.cise.ufl.edu/">https: </a><a href="https://cop3275.cise.ufl.edu/">//cop3275.cise.ufl.edu</a></li>

 <li>For guide on how to access the Judge, visit Judge Access Page under Pages section in Canvas.</li>

 <li>The judge will run test cases against your code and assign it a grade. You can have multiple submission for the same problem but you have to choose which one is the final (we will consider your final submission for grading). Canvas is only used for record keeping.</li>

 <li>When uploading on Canvas, zip your programs in a zipfile with your ufid as name (nothing more, just 8 digit ufid, for instance 12345678.zip). Add a .txt extension to all your files. i.e. name your files (inside the zipped archive) p1.c.txt, p2.c.txt, and so on.</li>

 <li>For all the problems input is read from standard input (e.g. read using scanf) and must be written to standard output (e.g. printf).</li>

 <li><strong>Don’t print extra stuff. Since the assignments are automatically graded, if the output doesn’t match the expected output, you will not get the points. </strong>For instance: If the problem is to read a number and return its square, the expected output is a number (i.e. printf(“%d”,i*i). If you print using something like printf(“square is %d”,i*i); you will not receive any points.</li>

 <li>The assignment is due on 11:59 pm Friday Nov. 1st, 2019. There is a 20% penalty for late submission of one day. No submission is accepted beyond that time.</li>

</ol>

<h1>Problem 1: Dense!                                                                   [20 Points]</h1>

Expected LoC: <em>&lt; </em>30

For this problem you are given two int arrays of the same length (let’s call them vectors). First compute and print (in a newline) the elementwise multiplication of them. Then determine and print (in a newline) if the given vectors are perpendicular to each other (i.e. if the inner product of them is zero, recall that inner product of vectors is the sum of elementwise multiplication).

Print “perpendicular” if they are perpendicular and “not perpendicular” otherwise (all lowercase). First, N is given as the length of each array. Second, N numbers follow corresponding to first vector and then another N numbers are given for the second vector. N is at most 100,000.

Note that even though each number fits an integer the product may not fit a regular integer. You should properly cast when multiplying the numbers together.

Examples:

<table width="530">

 <tbody>

  <tr>

   <td width="164">Input</td>

   <td width="175">Expected output</td>

   <td width="191">Explanation</td>

  </tr>

  <tr>

   <td width="164">75 0 20 10 -30 5 08 2 -1 2 0 1 20</td>

   <td width="175">40 0 -20 20 0 5 0 not perpendicular</td>

   <td width="191">The sum of element-wise products is not zero hence not perpendicular.</td>

  </tr>

  <tr>

   <td width="164">65 0 10 -5 -30 18 2 -3 1 0 -5</td>

   <td width="175">40 0 -30 -5 0 -5perpendicular</td>

   <td width="191">The sum of element-wise products is zero.</td>

  </tr>

 </tbody>

</table>

<h1>Problem 2: Check Mate!                                                        [80 points]</h1>

Expected LoC: <em>&lt; </em>200

In this problem you are given a chess board with pieces on (all formatted as characters). You task is to detect whether the <strong>black player </strong>is in check, or not threatened at all.

Input is given as 8 lines of 8 characters (8 characters following by ‘
’ for the first 7 lines, 8 characters for the 8th line). Upper case letters stand for white and lower-case letters stand for black pieces. Don’t assume the input is a proper/complete chess game (e.g. there might be all queens) but there always will be <em>exactly one king of each colour</em>. A hyphen “-“ stands for an empty cell. The output must be the number of opponent (white) pieces that can capture the black king.

You can read the pieces’ moves on Wikipedia <a href="https://en.wikipedia.org/wiki/Chess">(https://en.wikipedia.org/wiki/Chess).</a> In short, all pieces move and capture the same except for Pawn. Rook moves horizontally or vertically, Bishop moves diagonally, Knight has L shaped jumps, Queen moves like both Rook and Bishop, and King can move to its adjacent 8 cells only (a king cannot move to a cell where an opponent can capture it there). Pawn moves straight toward the opponent but can capture the piece on its immediate right or left diagonal cell towards the enemy (that is what matters for checking the king). Assume in our game White starts at the bottom and black starts at the top (so a White pawn can only move up or capture its immediate up-right or up-left piece).

The king is in check, if it is threatened by an enemy piece (i.e., the piece can capture the king). Find and print the number of white pieces that can capture the black king (if no piece threatens the king, then print 0 which means it is not a check situation).

Characters used to denote the pieces are:

White: K = king, Q = queen, R = rook, B = bishop, N = knight, P = pawn

Black: k = king, q = queen, r = rook, b = bishop, n = knight, p = pawn

Hints:

<ul>

 <li>Implement functions that reverse track the moves from the king until it reaches the first piece. That piece can attack the king if it’s capture move matches with the move that you tracked. e.g., a function that checks the whole row and column starting at king’s location and moving away until it reaches a piece; if that piece is Queen or Rook then it can capture the king.</li>

 <li>Read input properly. Remember scanf characteristics with characters and whitespaces (newlines). Store in a two-dimensional array.</li>

 <li>Always bound check the indices of the arrays.</li>

</ul>

Examples:

<table width="530">

 <tbody>

  <tr>

   <td width="148">Input</td>

   <td width="148">Expected output</td>

   <td width="233">Explanation</td>

  </tr>

  <tr>

   <td width="148">—r—k pp—-Qn –p—–——–——–P—–RP-PP—PK——–</td>

   <td width="148">1</td>

   <td width="233">The white queen is attacking the black king.</td>

  </tr>

  <tr>

   <td width="148">QP-nrPRRNR—-N--Bn—Bb—p—-B-BN—-—-r-Rb–k–K–-rB–p–</td>

   <td width="148">3</td>

   <td width="233">Bishop on up-left, Knight (N) on top-right, and Bishop on top-right from black king (k)’s position are attacking it.</td>

  </tr>

  <tr>

   <td width="148">QP—–RN—–N-–R—-b—p—-B——--qP-r—–kK—-—–p–</td>

   <td width="148">1</td>

   <td width="233">The Bishop on top-left and the Rook on the same column cannot capture the king since they are blocked by another piece (whether friendly or enemy). The only piece that can capture the black is the white king. If the wh ite king wasn’t there the answer would have been 0. Also the white Pawn above the king cannot capture it since its capture move is one-diagonal.</td>

  </tr>

 </tbody>

</table>

<h1>Problem 3: CHECKMATE!                                        [Extra 40 points]</h1>

Expected LoC: 400

If the king is in check and the player doesn’t have any move to get the king out of the check, it is checkmate and the player loses the match. A king may get out of the check by either moving out of the threatened cell (into a non-threatened one, potentially capturing the enemy attacker) or if another piece blocks the way of the opponent’s piece that can capture the king (or knocks out the opponent’s piece that is threatening the king). Note that the king might be threatened by two opponent pieces (more than one piece in general). In that case the only valid move is for the king to move to a non-threatened cell (and if it doesn’t have such a move, then it is checkmate).

Implement checkmate functionality. Input is same as before. Output is same as before, except when it is a checkmate, print 100. i.e. the example (with the picture above) is a case of checkmate. In this case you print 100 instead of 1. It is a checkmate because the attacking queen is being supported by a rook which means the king cannot capture the attacking queen (a king cannot move to a cell where it can be captured, in this case by the supporting rook).

<ol>

 <li>Note: this extra credit problem is substantially harder than problem 2 as you need to implement all the possible moves/captures for black player and all the captures for white player.</li>

 <li>In all cases if the king can move to a non-threatened cell, it is not a checkmate.</li>

 <li>You need to check if it is a single check (only one white piece can capture the king), if any black piece can block the attacking piece or capture it (if it can, it is not a checkmate). If the king cannot move to a non-threatened cell and if no other black piece can help, it is a checkmate and black loses the game.</li>

 <li>If it is a multi-check (more than one piece can capture the black king), the only possible way to get out of check is for the king to move to a cell where no other piece can capture it.</li>

</ol>

<em>Note: do not attempt this problem unless you have already done problem 2 and you have excessive free time on your hand!</em>

<em>Note 2: You need to pass at least 97 test cases for a partial credit (97 gives you 10 points, 98 gives you 20, 99 gives you 30 and 100 will give you 40 points). There is no partial credit for this problem below that.</em>