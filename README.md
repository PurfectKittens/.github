```cpp
#include <iostream>
#include <vector>
#include <iomanip>

class Membre {
public:
    Membre(const std::string& pseudo, int age, const std::string& poste)
        : pseudo(pseudo), age(age), poste(poste) {}

    void afficher() const {
        std::cout << std::left << std::setw(15) << "Pseudo:" << pseudo << "\n";
        std::cout << std::left << std::setw(15) << "Age:" << age << "\n";
        std::cout << std::left << std::setw(15) << "Poste:" << poste << "\n";
        std::cout << std::string(20, '-') << "\n";
    }

private:
    std::string pseudo;
    int age;
    std::string poste;
};

int main() {
    try {
        std::vector<Membre> membres;

        membres.emplace_back("Kittygirlyy", 18, "Dev");

        for (const auto& membre : membres) {
            membre.afficher();
        }
    }
    catch (const std::exception& e) {
        std::cerr << "Erreur: " << e.what() << "\n";
    }

    return 0;
}
```
