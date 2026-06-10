#include <iostream>
#include <string>
#include <cmath>

int num_iteration = 0;     // Global variables(except constant pi) //
double num_x;
double num_y;
double current_answer = 0;
double previous_answer = 0;

void show_nav()     // Navigation function that displays operators(commands) //
{

    std::cout << "      <------------------------------> <-------------------------------->\n";
    std::cout << "    |        < FULL SPRITE >                                              |\n";
    std::cout << "  |   <--------------------------->        -----   -----   -----   -----    |\n";
    std::cout << " |    |___________TYPE____________|       |     | |     | |     | |     |    |\n";
    std::cout << "|     | ->'?'  = guide            |       |  c  | |  p  | |  u  | |  e  |     |\n";
    std::cout << "|     | 'c'  = clear              |       |     | |     | |     | |     |     |\n";
    std::cout << "|     | '+'  = add                |        -----   -----   -----   -----      |\n";
    std::cout << "|     | '-'  = subtract           |   |    -----   -----   -----   -----      |\n";
    std::cout << "|     | '*'  = multiply           |   |   |     | |     | |     | |     |     |\n";
    std::cout << "|     | '/'  = divide             |  > <  |  +  | |  -  | |  *  | |  /  |     |\n";
    std::cout << "|     | 'u'  = pi(3.14)           |   |   |     | |     | |     | |     |     |\n";
    std::cout << "|     | '%'  = percent            |   |    -----   -----   -----   -----      |\n";
    std::cout << "|     | '^'  = square             |        -----   -----   -----   #####      |\n";
    std::cout << "|     | 'p'  = previous ans       |       |     | |     | |     | #     #     |\n";
    std::cout << "|     | 'e'  = exit               |       |  =  | |  %  | |  ^  | #  ?  #     |\n";
    std::cout << " |    |                           |       |     | |     | |     | #     #    |\n";
    std::cout << "  |   <--------------------------->        -----   -----   -----   #####    |\n";
    std::cout << "    |                                                                     |\n";
    std::cout << "      <------------------------------> <-------------------------------->\n";

}

void all_clear()     // Acts as the [AC] button rather than [DEL] which can still navigate previous ans //
{

    std::cout << "----------------------------------------------------------[Iteration " << num_iteration << "]\n\n";
    std::cout << "      <------------------------------> <-------------------------------->\n";
    std::cout << "    |        < FULL SPRITE >                                              |\n";
    std::cout << "  |   <--------------------------->        #####   -----   -----   -----    |\n";
    std::cout << " |    |___________TYPE____________|       #     # |     | |     | |     |    |\n";
    std::cout << "|     | '?'  = guide              |       #  c  # |  p  | |  u  | |  e  |     |\n";
    std::cout << "|     | ->'c'  = clear            |       #     # |     | |     | |     |     |\n";
    std::cout << "|     | '+'  = add                |        #####   -----   -----   -----      |\n";
    std::cout << "|     | '-'  = subtract           |   |    -----   -----   -----   -----      |\n";
    std::cout << "|     | '*'  = multiply           |   |   |     | |     | |     | |     |     |\n";
    std::cout << "|     | '/'  = divide             |  > <  |  +  | |  -  | |  *  | |  /  |     |\n";
    std::cout << "|     | 'u'  = pi(3.14)           |   |   |     | |     | |     | |     |     |\n";
    std::cout << "|     | '%'  = percent            |   |    -----   -----   -----   -----      |\n";
    std::cout << "|     | '^'  = square             |        -----   -----   -----   -----      |\n";
    std::cout << "|     | 'p'  = previous ans       |       |     | |     | |     | |     |     |\n";
    std::cout << "|     | 'e'  = exit               |       |  =  | |  %  | |  ^  | |  ?  |     |\n";
    std::cout << " |    |                           |       |     | |     | |     | |     |    |\n";
    std::cout << "  |   <--------------------------->        -----   -----   -----   -----    |\n";
    std::cout << "    |                                                                     |\n";
    std::cout << "      <------------------------------> <-------------------------------->\n\n";
    num_iteration += 1;
    previous_answer = 0;
    std::cout << "Previous answer has been cleared to " << previous_answer << ".\n\n";
    std::cout << "----------------------------------------------------------[End]\n";

}

void add_nums()
{

    num_iteration += 1;
    num_x = 0;
    num_y = 0;
    std::cout << "----------------------------------------------------------[Iteration " << num_iteration << "]\n\n";
    std::cout << "      <------------------------------> <-------------------------------->\n";
    std::cout << "    |        < FULL SPRITE >                                              |\n";
    std::cout << "  |   <--------------------------->        -----   -----   -----   -----    |\n";
    std::cout << " |    |___________TYPE____________|       |     | |     | |     | |     |    |\n";
    std::cout << "|     | '?'  = guide              |       |  c  | |  p  | |  u  | |  e  |     |\n";
    std::cout << "|     | 'c'  = clear              |       |     | |     | |     | |     |     |\n";
    std::cout << "|     | ->'+'  = add              |        -----   -----   -----   -----      |\n";
    std::cout << "|     | '-'  = subtract           |   |    #####   -----   -----   -----      |\n";
    std::cout << "|     | '*'  = multiply           |   |   #     # |     | |     | |     |     |\n";
    std::cout << "|     | '/'  = divide             |  > <  #  +  # |  -  | |  *  | |  /  |     |\n";
    std::cout << "|     | 'u'  = pi(3.14)           |   |   #     # |     | |     | |     |     |\n";
    std::cout << "|     | '%'  = percent            |   |    #####   -----   -----   -----      |\n";
    std::cout << "|     | '^'  = square             |        -----   -----   -----   -----      |\n";
    std::cout << "|     | 'p'  = previous ans       |       |     | |     | |     | |     |     |\n";
    std::cout << "|     | 'e'  = exit               |       |  =  | |  %  | |  ^  | |  ?  |     |\n";
    std::cout << " |    |                           |       |     | |     | |     | |     |    |\n";
    std::cout << "  |   <--------------------------->        -----   -----   -----   -----    |\n";
    std::cout << "    |                                                                     |\n";
    std::cout << "      <------------------------------> <-------------------------------->\n\n";
    std::cout << "-> x + y = z\n\n";
    std::cout << "x: ";
    std::cin >> num_x;
    std::cout << "y: ";
    std::cin >> num_y;
    std::cout << '\n';
    current_answer = num_x + num_y;
    std::cout << "-> " << num_x << " + " << num_y << " = " << current_answer << "\n\n";
    std::cout << "----------------------------------------------------------[End]\n";
    previous_answer = current_answer;
    current_answer = 0;
    num_x = 0;
    num_y = 0;

}

void subtract_nums()
{

    num_iteration += 1;
    num_x = 0;
    num_y = 0;
    std::cout << "----------------------------------------------------------[Iteration " << num_iteration << "]\n\n";
    std::cout << "      <------------------------------> <-------------------------------->\n";
    std::cout << "    |        < FULL SPRITE >                                              |\n";
    std::cout << "  |   <--------------------------->        -----   -----   -----   -----    |\n";
    std::cout << " |    |___________TYPE____________|       |     | |     | |     | |     |    |\n";
    std::cout << "|     | '?'  = guide              |       |  c  | |  p  | |  u  | |  e  |     |\n";
    std::cout << "|     | 'c'  = clear              |       |     | |     | |     | |     |     |\n";
    std::cout << "|     | '+'  = add                |        -----   -----   -----   -----      |\n";
    std::cout << "|     | ->'-'  = subtract         |   |    -----   #####   -----   -----      |\n";
    std::cout << "|     | '*'  = multiply           |   |   |     | #     # |     | |     |     |\n";
    std::cout << "|     | '/'  = divide             |  > <  |  +  | #  -  # |  *  | |  /  |     |\n";
    std::cout << "|     | 'u'  = pi(3.14)           |   |   |     | #     # |     | |     |     |\n";
    std::cout << "|     | '%'  = percent            |   |    -----   #####   -----   -----      |\n";
    std::cout << "|     | '^'  = square             |        -----   -----   -----   -----      |\n";
    std::cout << "|     | 'p'  = previous ans       |       |     | |     | |     | |     |     |\n";
    std::cout << "|     | 'e'  = exit               |       |  =  | |  %  | |  ^  | |  ?  |     |\n";
    std::cout << " |    |                           |       |     | |     | |     | |     |    |\n";
    std::cout << "  |   <--------------------------->        -----   -----   -----   -----    |\n";
    std::cout << "    |                                                                     |\n";
    std::cout << "      <------------------------------> <-------------------------------->\n\n";
    std::cout << "-> x - y = z\n\n";
    std::cout << "x: ";
    std::cin >> num_x;
    std::cout << "y: ";
    std::cin >> num_y;
    std::cout << '\n';
    current_answer = num_x - num_y;
    std::cout << "-> " << num_x << " - " << num_y << " = " << current_answer << "\n\n";
    std::cout << "----------------------------------------------------------[End]\n";
    previous_answer = current_answer;
    current_answer = 0;
    num_x = 0;
    num_y = 0;

}

void multiply_nums()
{

    num_iteration += 1;
    num_x = 0;
    num_y = 0;
    std::cout << "----------------------------------------------------------[Iteration " << num_iteration << "]\n\n";
    std::cout << "      <------------------------------> <-------------------------------->\n";
    std::cout << "    |        < FULL SPRITE >                                              |\n";
    std::cout << "  |   <--------------------------->        -----   -----   -----   -----    |\n";
    std::cout << " |    |___________TYPE____________|       |     | |     | |     | |     |    |\n";
    std::cout << "|     | '?'  = guide              |       |  c  | |  p  | |  u  | |  e  |     |\n";
    std::cout << "|     | 'c'  = clear              |       |     | |     | |     | |     |     |\n";
    std::cout << "|     | '+'  = add                |        -----   -----   -----   -----      |\n";
    std::cout << "|     | '-'  = subtract           |   |    -----   -----   #####   -----      |\n";
    std::cout << "|     | ->'*'  = multiply         |   |   |     | |     | #     # |     |     |\n";
    std::cout << "|     | '/'  = divide             |  > <  |  +  | |  -  | #  *  # |  /  |     |\n";
    std::cout << "|     | 'u'  = pi(3.14)           |   |   |     | |     | #     # |     |     |\n";
    std::cout << "|     | '%'  = percent            |   |    -----   -----   #####   -----      |\n";
    std::cout << "|     | '^'  = square             |        -----   -----   -----   -----      |\n";
    std::cout << "|     | 'p'  = previous ans       |       |     | |     | |     | |     |     |\n";
    std::cout << "|     | 'e'  = exit               |       |  =  | |  %  | |  ^  | |  ?  |     |\n";
    std::cout << " |    |                           |       |     | |     | |     | |     |    |\n";
    std::cout << "  |   <--------------------------->        -----   -----   -----   -----    |\n";
    std::cout << "    |                                                                     |\n";
    std::cout << "      <------------------------------> <-------------------------------->\n\n";
    std::cout << "-> x * y = z\n\n";
    std::cout << "x: ";
    std::cin >> num_x;
    std::cout << "y: ";
    std::cin >> num_y;
    std::cout << '\n';
    current_answer = num_x * num_y;
    std::cout << "-> " << num_x << " * " << num_y << " = " << current_answer << "\n\n";
    std::cout << "----------------------------------------------------------[End]\n";
    previous_answer = current_answer;
    current_answer = 0;
    num_x = 0;
    num_y = 0;

}

void divide_nums()
{

    num_iteration += 1;
    num_x = 0;
    num_y = 0;
    std::cout << "----------------------------------------------------------[Iteration " << num_iteration << "]\n\n";
    std::cout << "      <------------------------------> <-------------------------------->\n";
    std::cout << "    |        < FULL SPRITE >                                              |\n";
    std::cout << "  |   <--------------------------->        -----   -----   -----   -----    |\n";
    std::cout << " |    |___________TYPE____________|       |     | |     | |     | |     |    |\n";
    std::cout << "|     | '?'  = guide              |       |  c  | |  p  | |  u  | |  e  |     |\n";
    std::cout << "|     | 'c'  = clear              |       |     | |     | |     | |     |     |\n";
    std::cout << "|     | '+'  = add                |        -----   -----   -----   -----      |\n";
    std::cout << "|     | '-'  = subtract           |   |    -----   -----   -----   #####      |\n";
    std::cout << "|     | '*'  = multiply           |   |   |     | |     | |     | #     #     |\n";
    std::cout << "|     | ->'/'  = divide           |  > <  |  +  | |  -  | |  *  | #  /  #     |\n";
    std::cout << "|     | 'u'  = pi(3.14)           |   |   |     | |     | |     | #     #     |\n";
    std::cout << "|     | '%'  = percent            |   |    -----   -----   -----   #####      |\n";
    std::cout << "|     | '^'  = square             |        -----   -----   -----   -----      |\n";
    std::cout << "|     | 'p'  = previous ans       |       |     | |     | |     | |     |     |\n";
    std::cout << "|     | 'e'  = exit               |       |  =  | |  %  | |  ^  | |  ?  |     |\n";
    std::cout << " |    |                           |       |     | |     | |     | |     |    |\n";
    std::cout << "  |   <--------------------------->        -----   -----   -----   -----    |\n";
    std::cout << "    |                                                                     |\n";
    std::cout << "      <------------------------------> <-------------------------------->\n\n";
    std::cout << "-> x / y = z\n\n";
    std::cout << "x: ";
    std::cin >> num_x;
    std::cout << "y: ";
    std::cin >> num_y;
    std::cout << '\n';
    current_answer = num_x / num_y;
    std::cout << "-> " << num_x << " / " << num_y << " = " << current_answer << "\n\n";
    std::cout << "----------------------------------------------------------[End]\n";
    previous_answer = current_answer;
    current_answer = 0;
    num_x = 0;
    num_y = 0;

}

void pie_num()
{

    num_iteration += 1;
    num_x = 0;
    num_y = 0;
    std::cout << "----------------------------------------------------------[Iteration " << num_iteration << "]\n\n";
    std::cout << "      <------------------------------> <-------------------------------->\n";
    std::cout << "    |        < FULL SPRITE >                                              |\n";
    std::cout << "  |   <--------------------------->        -----   -----   #####   -----    |\n";
    std::cout << " |    |___________TYPE____________|       |     | |     | #     # |     |    |\n";
    std::cout << "|     | '?'  = guide              |       |  c  | |  p  | #  u  # |  e  |     |\n";
    std::cout << "|     | 'c'  = clear              |       |     | |     | #     # |     |     |\n";
    std::cout << "|     | '+'  = add                |        -----   -----   #####   -----      |\n";
    std::cout << "|     | '-'  = subtract           |   |    -----   -----   -----   -----      |\n";
    std::cout << "|     | '*'  = multiply           |   |   |     | |     | |     | |     |     |\n";
    std::cout << "|     | '/'  = divide             |  > <  |  +  | |  -  | |  *  | |  /  |     |\n";
    std::cout << "|     | ->'u'  = pi(3.14)         |   |   |     | |     | |     | |     |     |\n";
    std::cout << "|     | '%'  = percent            |   |    -----   -----   -----   -----      |\n";
    std::cout << "|     | '^'  = square             |        -----   -----   -----   -----      |\n";
    std::cout << "|     | 'p'  = previous ans       |       |     | |     | |     | |     |     |\n";
    std::cout << "|     | 'e'  = exit               |       |  =  | |  %  | |  ^  | |  ?  |     |\n";
    std::cout << " |    |                           |       |     | |     | |     | |     |    |\n";
    std::cout << "  |   <--------------------------->        -----   -----   -----   -----    |\n";
    std::cout << "    |                                                                     |\n";
    std::cout << "      <------------------------------> <-------------------------------->\n\n";
    std::cout << "Visual Pi: 3.1415926535897932384626433832795028841971693993751058209749445923078164062862089986280348253421...\n\n";
    std::cout << "----------------------------------------------------------[End]\n";

}

void percent_num()
{

    num_iteration += 1;
    current_answer = 0;
    num_x = 0;
    num_y = 0;
    char per_cent = ' ';
    std::cout << "----------------------------------------------------------[Iteration " << num_iteration << "]\n\n";
    std::cout << "      <------------------------------> <-------------------------------->\n";
    std::cout << "    |        < FULL SPRITE >                                              |\n";
    std::cout << "  |   <--------------------------->        -----   -----   -----   -----    |\n";
    std::cout << " |    |___________TYPE____________|       |     | |     | |     | |     |    |\n";
    std::cout << "|     | '?'  = guide              |       |  c  | |  p  | |  u  | |  e  |     |\n";
    std::cout << "|     | 'c'  = clear              |       |     | |     | |     | |     |     |\n";
    std::cout << "|     | '+'  = add                |        -----   -----   -----   -----      |\n";
    std::cout << "|     | '-'  = subtract           |   |    -----   -----   -----   -----      |\n";
    std::cout << "|     | '*'  = multiply           |   |   |     | |     | |     | |     |     |\n";
    std::cout << "|     | '/'  = divide             |  > <  |  +  | |  -  | |  *  | |  /  |     |\n";
    std::cout << "|     | 'u'  = pi(3.14)           |   |   |     | |     | |     | |     |     |\n";
    std::cout << "|     | ->'%'  = percent          |   |    -----   -----   -----   -----      |\n";
    std::cout << "|     | '^'  = square             |        -----   #####   -----   -----      |\n";
    std::cout << "|     | 'p'  = previous ans       |       |     | #     # |     | |     |     |\n";
    std::cout << "|     | 'e'  = exit               |       |  =  | #  %  # |  ^  | |  ?  |     |\n";
    std::cout << " |    |                           |       |     | #     # |     | |     |    |\n";
    std::cout << "  |   <--------------------------->        -----   #####   -----   -----    |\n";
    std::cout << "    |                                                                     |\n";
    std::cout << "      <------------------------------> <-------------------------------->\n\n";
    std::cout << "[Type sub-command]:\n";
    std::cout << "'a' = conversion from # -> % (Ex: Test score)\n";
    std::cout << "'b' = conversion from % -> # (Ex: Item discount)\n";
    std::cout << "'c' = conversion from % -> # (Ex: Item tax)\n\n";   // Will add this feature below 'b' as almost the same except '+' at the end //
    std::cin >> per_cent;

    if (per_cent == 'a' || per_cent == 'A')
    {

        std::cout << "----------------------------------------------------------[Iteration " << num_iteration << "a]\n\n";
        std::cout << "      <------------------------------> <-------------------------------->\n";
        std::cout << "    |        < FULL SPRITE >                                              |\n";
        std::cout << "  |   <--------------------------->        -----   -----   -----   -----    |\n";
        std::cout << " |    |___________TYPE____________|       |     | |     | |     | |     |    |\n";
        std::cout << "|     | '?'  = guide              |       |  c  | |  p  | |  u  | |  e  |     |\n";
        std::cout << "|     | 'c'  = clear              |       |     | |     | |     | |     |     |\n";
        std::cout << "|     | '+'  = add                |        -----   -----   -----   -----      |\n";
        std::cout << "|     | '-'  = subtract           |   |    -----   -----   -----   -----      |\n";
        std::cout << "|     | '*'  = multiply           |   |   |     | |     | |     | |     |     |\n";
        std::cout << "|     | '/'  = divide             |  > <  |  +  | |  -  | |  *  | |  /  |     |\n";
        std::cout << "|     | 'u'  = pi(3.14)           |   |   |     | |     | |     | |     |     |\n";
        std::cout << "|     | ->'%'  = percent          |   |    -----   -----   -----   -----      |\n";
        std::cout << "|     | '^'  = square             |        -----   #####   -----   -----      |\n";
        std::cout << "|     | 'p'  = previous ans       |       |     | #     # |     | |     |     |\n";
        std::cout << "|     | 'e'  = exit               |       |  =  | #  %  # |  ^  | |  ?  |     |\n";
        std::cout << " |    |                           |       |     | #     # |     | |     |    |\n";
        std::cout << "  |   <--------------------------->        -----   #####   -----   -----    |\n";
        std::cout << "    |                                                                     |\n";
        std::cout << "      <------------------------------> <-------------------------------->\n\n";
        std::cout << "Given: x / X\n";
        std::cout << "Let x = Points earned\n";
        std::cout << "Let X = Points possible\n\n";
        std::cout << "x: ";
        std::cin >> num_x;
        std::cout << "X: ";
        std::cin >> num_y;
        current_answer = (num_x / num_y) * 100;
        std::cout << "\n-> " << current_answer << "%\n";
        std::cout << "----------------------------------------------------------[End]\n";
        previous_answer = current_answer;
        current_answer = 0;

    }

    else if (per_cent == 'b' || per_cent == 'B')
    {

        std::cout << "----------------------------------------------------------[Iteration " << num_iteration << "b]\n\n";
        std::cout << "      <------------------------------> <-------------------------------->\n";
        std::cout << "    |        < FULL SPRITE >                                              |\n";
        std::cout << "  |   <--------------------------->        -----   -----   -----   -----    |\n";
        std::cout << " |    |___________TYPE____________|       |     | |     | |     | |     |    |\n";
        std::cout << "|     | '?'  = guide              |       |  c  | |  p  | |  u  | |  e  |     |\n";
        std::cout << "|     | 'c'  = clear              |       |     | |     | |     | |     |     |\n";
        std::cout << "|     | '+'  = add                |        -----   -----   -----   -----      |\n";
        std::cout << "|     | '-'  = subtract           |   |    -----   -----   -----   -----      |\n";
        std::cout << "|     | '*'  = multiply           |   |   |     | |     | |     | |     |     |\n";
        std::cout << "|     | '/'  = divide             |  > <  |  +  | |  -  | |  *  | |  /  |     |\n";
        std::cout << "|     | 'u'  = pi(3.14)           |   |   |     | |     | |     | |     |     |\n";
        std::cout << "|     | ->'%'  = percent          |   |    -----   -----   -----   -----      |\n";
        std::cout << "|     | '^'  = square             |        -----   #####   -----   -----      |\n";
        std::cout << "|     | 'p'  = previous ans       |       |     | #     # |     | |     |     |\n";
        std::cout << "|     | 'e'  = exit               |       |  =  | #  %  # |  ^  | |  ?  |     |\n";
        std::cout << " |    |                           |       |     | #     # |     | |     |    |\n";
        std::cout << "  |   <--------------------------->        -----   #####   -----   -----    |\n";
        std::cout << "    |                                                                     |\n";
        std::cout << "      <------------------------------> <-------------------------------->\n\n";
        std::cout << "Given: X - x\n";
        std::cout << "Let X = Retail price\n";
        std::cout << "Let x = Amount discounted(number only; do not include '%' sign))\n\n";
        std::cout << "X: ";
        std::cin >> num_y;
        std::cout << "x: ";
        std::cin >> num_x;
        current_answer = num_y * (num_x / 100);
        previous_answer = current_answer;
        current_answer = 0;
        current_answer = num_y - previous_answer;
        std::cout << "\n-> -$" << previous_answer << " or $" << current_answer << " after applied discount.\n\n";
        std::cout << "----------------------------------------------------------[End]\n";
        previous_answer = current_answer;
        current_answer = 0;


    }

    else if (per_cent == 'c' || per_cent == 'C')
    {

        std::cout << "----------------------------------------------------------[Iteration " << num_iteration << "c]\n\n";
        std::cout << "      <------------------------------> <-------------------------------->\n";
        std::cout << "    |        < FULL SPRITE >                                              |\n";
        std::cout << "  |   <--------------------------->        -----   -----   -----   -----    |\n";
        std::cout << " |    |___________TYPE____________|       |     | |     | |     | |     |    |\n";
        std::cout << "|     | '?'  = guide              |       |  c  | |  p  | |  u  | |  e  |     |\n";
        std::cout << "|     | 'c'  = clear              |       |     | |     | |     | |     |     |\n";
        std::cout << "|     | '+'  = add                |        -----   -----   -----   -----      |\n";
        std::cout << "|     | '-'  = subtract           |   |    -----   -----   -----   -----      |\n";
        std::cout << "|     | '*'  = multiply           |   |   |     | |     | |     | |     |     |\n";
        std::cout << "|     | '/'  = divide             |  > <  |  +  | |  -  | |  *  | |  /  |     |\n";
        std::cout << "|     | 'u'  = pi(3.14)           |   |   |     | |     | |     | |     |     |\n";
        std::cout << "|     | ->'%'  = percent          |   |    -----   -----   -----   -----      |\n";
        std::cout << "|     | '^'  = square             |        -----   #####   -----   -----      |\n";
        std::cout << "|     | 'p'  = previous ans       |       |     | #     # |     | |     |     |\n";
        std::cout << "|     | 'e'  = exit               |       |  =  | #  %  # |  ^  | |  ?  |     |\n";
        std::cout << " |    |                           |       |     | #     # |     | |     |    |\n";
        std::cout << "  |   <--------------------------->        -----   #####   -----   -----    |\n";
        std::cout << "    |                                                                     |\n";
        std::cout << "      <------------------------------> <-------------------------------->\n\n";
        std::cout << "Given: X + x\n";
        std::cout << "Let X = Retail price\n";
        std::cout << "Let x = Included tax(number only; do not include '%' sign))\n\n";
        std::cout << "X: ";
        std::cin >> num_y;
        std::cout << "x: ";
        std::cin >> num_x;
        current_answer = num_y * (num_x / 100);
        previous_answer = current_answer;
        current_answer = 0;
        current_answer = num_y + previous_answer;
        std::cout << "\n-> +$" << previous_answer << " or $" << current_answer << " after tax.\n\n";
        std::cout << "----------------------------------------------------------[End]\n";
        previous_answer = current_answer;
        current_answer = 0;

    }

}

void square_num()
{

    num_iteration += 1;
    num_x = 0;
    num_y = 0;
    std::cout << "----------------------------------------------------------[Iteration " << num_iteration << "]\n\n";
    std::cout << "      <------------------------------> <-------------------------------->\n";
    std::cout << "    |        < FULL SPRITE >                                              |\n";
    std::cout << "  |   <--------------------------->        -----   -----   -----   -----    |\n";
    std::cout << " |    |___________TYPE____________|       |     | |     | |     | |     |    |\n";
    std::cout << "|     | '?'  = guide              |       |  c  | |  p  | |  u  | |  e  |     |\n";
    std::cout << "|     | 'c'  = clear              |       |     | |     | |     | |     |     |\n";
    std::cout << "|     | '+'  = add                |        -----   -----   -----   -----      |\n";
    std::cout << "|     | '-'  = subtract           |   |    -----   -----   -----   -----      |\n";
    std::cout << "|     | '*'  = multiply           |   |   |     | |     | |     | |     |     |\n";
    std::cout << "|     | '/'  = divide             |  > <  |  +  | |  -  | |  *  | |  /  |     |\n";
    std::cout << "|     | 'u'  = pi(3.14)           |   |   |     | |     | |     | |     |     |\n";
    std::cout << "|     | '%'  = percent            |   |    -----   -----   -----   -----      |\n";
    std::cout << "|     | ->'^'  = square           |        -----   -----   #####   -----      |\n";
    std::cout << "|     | 'p'  = previous ans       |       |     | |     | #     # |     |     |\n";
    std::cout << "|     | 'e'  = exit               |       |  =  | |  %  | #  ^  # |  ?  |     |\n";
    std::cout << " |    |                           |       |     | |     | #     # |     |    |\n";
    std::cout << "  |   <--------------------------->        -----   -----   #####   -----    |\n";
    std::cout << "    |                                                                     |\n";
    std::cout << "      <------------------------------> <-------------------------------->\n\n";
    std::cout << "Given: X^x\n";
    std::cout << "Let X = Base\n";
    std::cout << "Let x = Exponent\n\n";
    std::cout << "X: ";
    std::cin >> num_y;
    std::cout << "x: ";
    std::cin >> num_x;
    std::cout << '\n' << num_y << "^" << num_x << " = " << num_y;

    for (int i = 1; i < num_x; i++)
    {

        std::cout << " * " << num_y;

    }
    current_answer = std::pow(num_y, num_x);     // X^x //
    std::cout << '\n' << "-> " << current_answer << '\n';
    previous_answer = current_answer;
    current_answer = 0;
    std::cout << "----------------------------------------------------------[End]\n";

}

void prev_ans_num()
{

    std::cout << "----------------------------------------------------------[Iteration " << num_iteration << "]\n\n";
    std::cout << "      <------------------------------> <-------------------------------->\n";
    std::cout << "    |        < FULL SPRITE >                                              |\n";
    std::cout << "  |   <--------------------------->        -----   #####   -----   -----    |\n";
    std::cout << " |    |___________TYPE____________|       |     | #     # |     | |     |    |\n";
    std::cout << "|     | '?'  = guide              |       |  c  | #  p  # |  u  | |  e  |     |\n";
    std::cout << "|     | 'c'  = clear              |       |     | #     # |     | |     |     |\n";
    std::cout << "|     | '+'  = add                |        -----   #####   -----   -----      |\n";
    std::cout << "|     | '-'  = subtract           |   |    -----   -----   -----   -----      |\n";
    std::cout << "|     | '*'  = multiply           |   |   |     | |     | |     | |     |     |\n";
    std::cout << "|     | '/'  = divide             |  > <  |  +  | |  -  | |  *  | |  /  |     |\n";
    std::cout << "|     | 'u'  = pi(3.14)           |   |   |     | |     | |     | |     |     |\n";
    std::cout << "|     | '%'  = percent            |   |    -----   -----   -----   -----      |\n";
    std::cout << "|     | '^'  = square             |        -----   -----   -----   -----      |\n";
    std::cout << "|     | ->'p'  = previous ans     |       |     | |     | |     | |     |     |\n";
    std::cout << "|     | 'e'  = exit               |       |  =  | |  %  | |  ^  | |  ?  |     |\n";
    std::cout << " |    |                           |       |     | |     | |     | |     |    |\n";
    std::cout << "  |   <--------------------------->        -----   -----   -----   -----    |\n";
    std::cout << "    |                                                                     |\n";
    std::cout << "      <------------------------------> <-------------------------------->\n\n";
    std::cout << "Visual Previous Answer: " << previous_answer << '\n' << '\n';
    std::cout << "----------------------------------------------------------[End]\n";

}

int main()
{

    std::cout << "Press [Enter] to begin.\n";
    std::cin.ignore();
    std::cout << "      <------------------------------> <-------------------------------->\n";
    std::cout << "    |        < FULL SPRITE >                                              |\n";
    std::cout << "  |   <--------------------------->        -----   -----   -----   -----    |\n";
    std::cout << " |    |___________TYPE____________|       |     | |     | |     | |     |    |\n";
    std::cout << "|     | '?'  = guide              |       |  c  | |  p  | |  u  | |  e  |     |\n";
    std::cout << "|     | 'c'  = clear              |       |     | |     | |     | |     |     |\n";
    std::cout << "|     | '+'  = add                |        -----   -----   -----   -----      |\n";
    std::cout << "|     | '-'  = subtract           |   |    -----   -----   -----   -----      |\n";
    std::cout << "|     | '*'  = multiply           |   |   |     | |     | |     | |     |     |\n";
    std::cout << "|     | '/'  = divide             |  > <  |  +  | |  -  | |  *  | |  /  |     |\n";
    std::cout << "|     | 'u'  = pi(3.14)           |   |   |     | |     | |     | |     |     |\n";
    std::cout << "|     | '%'  = percent            |   |    -----   -----   -----   -----      |\n";
    std::cout << "|     | '^'  = square             |        -----   -----   -----   -----      |\n";
    std::cout << "|     | 'p'  = previous ans       |       |     | |     | |     | |     |     |\n";
    std::cout << "|     | 'e'  = exit               |       |  =  | |  %  | |  ^  | |  ?  |     |\n";
    std::cout << " |    |                           |       |     | |     | |     | |     |    |\n";
    std::cout << "  |   <--------------------------->        -----   -----   -----   -----    |\n";
    std::cout << "    |                                                                     |\n";
    std::cout << "      <------------------------------> <-------------------------------->\n";



    char oper_ator = ' ';     // The operators are essentially the main command prompts as an empty character //

    while (oper_ator != 'e' && oper_ator != 'E')     // This loop is so that the user can have as many iterations as needed, as //
    {                                                // as long as the user does not type an input failure or an 'e' character //

        oper_ator = 'e';     // This work globally for in-function subcommand input failure //
        std::cout << "Proceed with command: ";     // Asks for command before iterating through ifs as 'h' for example //
        std::cin >> oper_ator;

        if (oper_ator == '?')     // Though I could have used cases here instead I find 'if-else' to be more intuitive for editing //
        {

            show_nav();

        }

        else if (oper_ator == 'c' || oper_ator == 'C')
        {

            all_clear();

        }

        else if (oper_ator == '+')
        {

            add_nums();

        }

        else if (oper_ator == '-')
        {

            subtract_nums();

        }

        else if (oper_ator == '*')
        {

            multiply_nums();

        }

        else if (oper_ator == '/')
        {

            divide_nums();

        }

        else if (oper_ator == 'u' || oper_ator == 'U')
        {

            pie_num();

        }

        else if (oper_ator == '%')
        {

            percent_num();

        }

        else if (oper_ator == '^')
        {

            square_num();

        }

        else if (oper_ator == 'p' || oper_ator == 'P')
        {

            prev_ans_num();

        }

        else
        {

            oper_ator = 'e';     // This works globally for main command input failure in function calling //

        }

    }
std::cout << "      <------------------------------> <-------------------------------->\n";
std::cout << "    |        < FULL SPRITE >                                              |\n";
std::cout << "  |   <--------------------------->        -----   -----   -----   #####    |\n";
std::cout << " |    |___________TYPE____________|       |     | |     | |     | #     #    |\n";
std::cout << "|     | ->'?'  = guide            |       |  c  | |  p  | |  u  | #  e  #     |\n";
std::cout << "|     | 'c'  = clear              |       |     | |     | |     | #     #     |\n";
std::cout << "|     | '+'  = add                |        -----   -----   -----   #####      |\n";
std::cout << "|     | '-'  = subtract           |   |    -----   -----   -----   -----      |\n";
std::cout << "|     | '*'  = multiply           |   |   |     | |     | |     | |     |     |\n";
std::cout << "|     | '/'  = divide             |  > <  |  +  | |  -  | |  *  | |  /  |     |\n";
std::cout << "|     | 'u'  = pi(3.14)           |   |   |     | |     | |     | |     |     |\n";
std::cout << "|     | '%'  = percent            |   |    -----   -----   -----   -----      |\n";
std::cout << "|     | '^'  = square             |        -----   -----   -----   -----      |\n";
std::cout << "|     | 'p'  = previous ans       |       |     | |     | |     | |     |     |\n";
std::cout << "|     | ->'e'  = exit             |       |  =  | |  %  | |  ^  | |  ?  |     |\n";
std::cout << " |    |                           |       |     | |     | |     | |     |    |\n";
std::cout << "  |   <--------------------------->        -----   -----   -----   -----    |\n";
std::cout << "    |                                                                     |\n";
std::cout << "      <------------------------------> <-------------------------------->\n";
return 0;
}
