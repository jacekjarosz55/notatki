



# Zadania do wykonania
 
## 1. Przygotuj klasę zawierającą pola i metody dla: Samochodu, Telefonu i Samolotu.

### Samochód:

```cpp
class Car {
protected:
    unsigned int kmDriven;
    std::string make;
    std::string model;
    std::string color;
    unsigned int year;
    unsigned int cost;
    unsigned int seatCount;
    bool manualGearbox;
public:
	
	    Car(unsigned int kmDriven, std::string make, std::string model, std::string color, unsigned int year, unsigned int cost, unsigned int seatCount, bool manualGearbox) : kmDriven(kmDriven),
	        make(make),
	        model(model),
	        color(color),
	        year(year),
	        cost(cost),
	        seatCount(seatCount),
	        manualGearbox(manualGearbox) {}
	
	
	void setKmDriven(unsigned int kmDriven) { this->kmDriven = kmDriven; }
	unsigned int getKmDriven() { return this->kmDriven; }
	
	void setMake(std::string make) { this->make = make; }
	std::string getMake() { return this->make; }
	
	void setModel(std::string model) { this->model = model; }
	std::string getModel() { return this->model; }
	
	void setColor(std::string color) { this->color = color; }
	std::string getColor() { return this->color; }
	
	void setYear(unsigned int year) { this->year = year; }
	unsigned int getYear() { return this->year; }
	
	void setCost(unsigned int cost) { this->cost = cost; }
	unsigned int getCost() { return this->cost; }
	
	void setSeatCount(unsigned int seatCount) { this->seatCount = seatCount; }
	unsigned int getSeatCount() { return this->seatCount; }
	
	void setManualGearbox(bool manualGearbox) { this->manualGearbox = manualGearbox; }
	bool getManualGearbox() { return this->manualGearbox; }
	
	void drive(int km) {
	    kmDriven += km;
	}
	
	void scratch() {
	    color = "scratched";
	
	
	    long int newCost =  cost - 1000;
	    if (newCost < 0) {
	        cost = 0;
	    } else {
	        cost = newCost;
	    }
	}
};
```

### Samolot:

```cpp
class Plane {
public:
    std::string getName() const {
        return name;
    }

    void setName(const std::string& newName) {
        name = newName;
    }

    std::string getColor() const {
        return color;
    }

    void setColor(const std::string& newColor) {
        color = newColor;
    }

    int getCost() const {
        return cost;
    }

    void setCost(int newCost) {
        cost = newCost;
    }

    unsigned int getSeatCount() const {
        return seatCount;
    }

    void setSeatCount(unsigned int newSeatCount) {
        seatCount = newSeatCount;
    }

private:
    std::string name;
    std::string color;
    int cost;
    unsigned int seatCount;
};
```

### Telefon

```cpp
class Phone {
public:
    std::string getSerialNumber() const {
        return serialNumber;
    }

    void setSerialNumber(const std::string& newSerialNumber) {
        serialNumber = newSerialNumber;
    }

    std::string getPinNumber() const {
        return pinNumber;
    }

    void setPinNumber(const std::string& newPinNumber) {
        pinNumber = newPinNumber;
    }

    std::string getPhoneNumber() const {
        return phoneNumber;
    }

    void setPhoneNumber(const std::string& newPhoneNumber) {
        phoneNumber = newPhoneNumber;
    }

    int getCost() const {
        return cost;
    }

    void setCost(int newCost) {
        cost = newCost;
    }

private:
    std::string serialNumber;
    std::string pinNumber;
    std::string phoneNumber;
    int cost;
};
```


## 2.Przygotuj klasę zawierającą prostą implementację stosu.
```cpp
template <typename T>
class Stack {
protected:
    std::vector<T> container = {};
public:
    Stack() {}

    bool empty() {
        return container.empty();
    }

    void push(T value) {
        container.push_back(value);
    }
    T pop() {
        T val = container.back();
        container.pop_back();
        return val;
    }
};```


## 3. Przygotuj klasę zawierającą pola i metody dla Osoby.

```cpp
class Osoba
{
protected:
    std::string name;
    std::string surname;
    int age;

public:

    Osoba(std::string name, std::string surname, int age) : name(name), surname(surname), age(age) {}

    void sayHello() const {
        std::cout << "Hello, my name is " << name << " " << surname << ", and I'm " << age << " years old." << std::endl;
    }

    void setName(std::string newName)
    {
        if(name != "")
        {
            name = newName;
        }
    }

    std::string getName() const {
        return name;
    }

    void setSurname(std::string newSurname) {
        if (surname != "") {
            surname = newSurname;
        }
    }
    std::string getSurname() const {
        return surname;
    }

    void setAge(int newAge) {
        age = newAge;
    }
    int getAge() const {
        return age;
    }
};
```

## 4. Za pomocą klasy Vector stwórz kolekcję Osób.

```cpp
class PersonCollection {
private:
    std::vector<Osoba> container;
public:
	void push_osoba(const Osoba &osoba) {
		container.push_back(osoba);
	}
	std::vector<Osoba> get_vector() const {
		return container;
	}
};
```


## 5. Zapoznaj się z metodą przeszukiwania kolekcji za pomocą iteratorów.

```cpp
std::vector<Osoba> osoby;
Osoba os1("Kuba", "Kubanczyk", 33);
osoby.addPerson(os1);
os1.setName("Jacek");
os1.setSurname("Jarosz");
os1.setAge(20);
osoby.addPerson(os1);
os1.setName("Jacek");
os1.setSurname("Baczek");
os1.setAge(21);
osoby.addPerson(os1);

for(auto it = osoby.begin(); it != osoby.end(); ++it ) {
	if(it->getName() == "Jacek") {
		it->sayHello();
	}
}
```


## 6. Przygotuj metody pozwalające na wyszukiwanie Osób po imionach, nazwiskach, adresach itd. z kolekcji Osób.

```cpp
class PersonCollection {
private:
    std::vector<Osoba> container;
public:
void addPerson(Osoba os) {
    container.push_back(os);
}

std::vector<Osoba> getPersonsByName(std::string searchedName) {
    std::vector<Osoba> foundPersons;
    for (int i = 0; i < container.size(); i++) {
        if(container[i].getName() == searchedName)
        {
            foundPersons.push_back(container[i]);
        }
    }
    return foundPersons;
}

std::vector<Osoba> getPersonsByAge(int searchedAge) {
    std::vector<Osoba> foundPersons;
    for (int i = 0; i < container.size(); i++) {
        if(container[i].getAge() == searchedAge)
        {
            foundPersons.push_back(container[i]);
        }
    }
    return foundPersons;
}
std::vector<Osoba> getPersonsBySurname(std::string searchedSurname) {
    std::vector<Osoba> foundPersons;
    for (int i = 0; i < container.size(); i++) {
        if(container[i].getSurname() == searchedSurname)
        {
            foundPersons.push_back(container[i]);
        }
    }
    return foundPersons;
}
};
```




