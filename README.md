#include <iostream>
#include <vector>
#include <cmath>
#include "matplotlibcpp.h"

namespace plt = matplotlibcpp;

int main() {
    double a = 1.0;  // Radio del círculo rodante
    int puntos = 1000;
    double t_min = 0.0, t_max = 4 * M_PI;  // Un cicloide completo

    std::vector<double> x, y;
    
    for (int i = 0; i < puntos; ++i) {
        double t = t_min + i * (t_max - t_min) / puntos;
        x.push_back(a * (t - sin(t)));
        y.push_back(a * (1 - cos(t)));
    }

    plt::plot(x, y);
    plt::xlabel("x");
    plt::ylabel("y");
    plt::title("Cicloide");
    plt::grid(true);
    plt::show();

    return 0;
}
