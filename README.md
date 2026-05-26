# Simple-Gaming-Character-System
#include <iostream>
using namespace std;

class GameCharacter
{
private:
    string name;
    int health;
    int attackPower;

public:
    // Constructor
    GameCharacter(string n, int h, int a)
    {
        name = n;
        health = h;
        attackPower = a;
    }

    // Display character details
    void display()
    {
        cout << "\nCharacter Details" << endl;
        cout << "Name : " << name << endl;
        cout << "Health : " << health << endl;
        cout << "Attack Power : " << attackPower << endl;
    }

    // Attack function
    void attack()
    {
        cout << name << " attacks with power "
             << attackPower << "!" << endl;
    }

    // Take damage
    void takeDamage(int damage)
    {
        health = health - damage;

        if (health < 0)
        {
            health = 0;
        }

        cout << name << " takes "
             << damage << " damage." << endl;
    }
};

int main()
{
    // Creating characters
    GameCharacter player1("Warrior", 100, 20);
    GameCharacter player2("Ninja", 80, 25);

    // Display details
    player1.display();
    player2.display();

    // Battle actions
    player1.attack();
    player2.takeDamage(20);

    player2.attack();
    player1.takeDamage(25);

    // Final details
    player1.display();
    player2.display();

    return 0;
}
