---
{"dg-publish":true,"permalink":"/GEANT4 Execution Plan/","tags":["Physics","coding","idea"]}
---


---
# Execution Plan
To simulate the described nuclear reaction using GEANT4, you will need to set up a simulation environment that models the neutron interactions with Thorium-232 (Th-232), and the subsequent decay processes leading to Uranium-233 (U-233). Here’s a basic outline of how to create a GEANT4 application for this purpose:

1. *Setup GEANT4 Environment*: Ensure you have GEANT4 installed and properly configured on your system.

2. *Create a New GEANT4 Application*: Start by creating a new GEANT4 application. This involves creating several files: CMakeLists.txt, main.cc, MyDetectorConstruction.hh, MyDetectorConstruction.cc, MyPrimaryGeneratorAction.hh, MyPrimaryGeneratorAction.cc, and MyPhysicsList.cc.

3. *Define the Detector Geometry*: In MyDetectorConstruction, define the geometry of your detector. For simplicity, you can start with a single volume that contains Thorium-232.

4. *Define the Primary Particle Generator*: In MyPrimaryGeneratorAction, define the neutron source and its initial conditions.

5. *Implement the Physics Processes*: In MyPhysicsList, add the necessary physics processes for neutron interactions, radioactive decay, and other relevant processes.

Here is a simplified version of these steps:

*CMakeLists.txt*
```cmake
cmake_minimum_required(VERSION 3.5)
project(ThoriumReactor)

find_package(Geant4 REQUIRED)
include(${Geant4_USE_FILE})

add_executable(ThoriumReactor main.cc MyDetectorConstruction.cc MyPrimaryGeneratorAction.cc MyPhysicsList.cc)
target_link_libraries(ThoriumReactor ${Geant4_LIBRARIES})
```


*main.cc*
```cpp
#include "G4RunManager.hh"
#include "G4UImanager.hh"
#include "QGSP_BIC.hh"

#include "MyDetectorConstruction.hh"
#include "MyPrimaryGeneratorAction.hh"
#include "MyPhysicsList.hh"

int main(int argc, char** argv) {
    G4RunManager* runManager = new G4RunManager();

    runManager->SetUserInitialization(new MyDetectorConstruction());
    runManager->SetUserInitialization(new MyPhysicsList());
    runManager->SetUserAction(new MyPrimaryGeneratorAction());

    runManager->Initialize();

    G4UImanager* UImanager = G4UImanager::GetUIpointer();
    UImanager->ApplyCommand("/run/initialize");
    UImanager->ApplyCommand("/run/beamOn 10000");

    delete runManager;
    return 0;
}
```

*MyDetectorConstruction.hh*
```cpp
#ifndef MyDetectorConstruction_h
#define MyDetectorConstruction_h 1

#include "G4VUserDetectorConstruction.hh"

class MyDetectorConstruction : public G4VUserDetectorConstruction {
public:
    MyDetectorConstruction();
    virtual ~MyDetectorConstruction();

    virtual G4VPhysicalVolume* Construct();
};

#endif
```

*MyDetectorConstruction.cc*
```cpp
#include "MyDetectorConstruction.hh"
#include "G4Material.hh"
#include "G4NistManager.hh"
#include "G4Box.hh"
#include "G4LogicalVolume.hh"
#include "G4PVPlacement.hh"
#include "G4SystemOfUnits.hh"

MyDetectorConstruction::MyDetectorConstruction() : G4VUserDetectorConstruction() {}

MyDetectorConstruction::~MyDetectorConstruction() {}

G4VPhysicalVolume* MyDetectorConstruction::Construct() {
    G4NistManager* nist = G4NistManager::Instance();
    G4Material* thorium = nist->FindOrBuildMaterial("G4_Th");

    G4Box* solidWorld = new G4Box("World", 1*m, 1*m, 1*m);
    G4LogicalVolume* logicWorld = new G4LogicalVolume(solidWorld, thorium, "World");
    G4VPhysicalVolume* physWorld = new G4PVPlacement(0, G4ThreeVector(), logicWorld, "World", 0, false, 0, true);

    return physWorld;
}
```

*MyPrimaryGeneratorAction.hh*
```cpp
#ifndef MyPrimaryGeneratorAction_h
#define MyPrimaryGeneratorAction_h 1

#include "G4VUserPrimaryGeneratorAction.hh"
#include "G4ParticleGun.hh"
#include "G4GeneralParticleSource.hh"

class MyPrimaryGeneratorAction : public G4VUserPrimaryGeneratorAction {
public:
    MyPrimaryGeneratorAction();
    virtual ~MyPrimaryGeneratorAction();

    virtual void GeneratePrimaries(G4Event*);
private:
    G4ParticleGun* fParticleGun;
};

#endif
```


*MyPrimaryGeneratorAction.cc*
```cpp
#include "MyPrimaryGeneratorAction.hh"
#include "G4ParticleGun.hh"
#include "G4ParticleTable.hh"
#include "G4ParticleDefinition.hh"
#include "G4SystemOfUnits.hh"

MyPrimaryGeneratorAction::MyPrimaryGeneratorAction() {
    G4int n_particle = 1;
    fParticleGun = new G4ParticleGun(n_particle);

    G4ParticleTable* particleTable = G4ParticleTable::GetParticleTable();
    G4ParticleDefinition* particle = particleTable->FindParticle("neutron");

    fParticleGun->SetParticleDefinition(particle);
    fParticleGun->SetParticleEnergy(14.1*MeV);
    fParticleGun->SetParticlePosition(G4ThreeVector(0., 0., 0.));
    fParticleGun->SetParticleMomentumDirection(G4ThreeVector(1.,0.,0.));
}

MyPrimaryGeneratorAction::~MyPrimaryGeneratorAction() {
    delete fParticleGun;
}

void MyPrimaryGeneratorAction::GeneratePrimaries(G4Event* anEvent) {
    fParticleGun->GeneratePrimaryVertex(anEvent);
}


*MyPhysicsList.hh*
```cpp
#ifndef MyPhysicsList_h
#define MyPhysicsList_h 1

#include "G4VModularPhysicsList.hh"

class MyPhysicsList : public G4VModularPhysicsList {
public:
    MyPhysicsList();
    virtual ~MyPhysicsList();
};

#endif
```


*MyPhysicsList.cc*
```cpp
#include "MyPhysicsList.hh"
#include "G4DecayPhysics.hh"
#include "G4RadioactiveDecayPhysics.hh"
#include "G4NeutronPhysics.hh"

MyPhysicsList::MyPhysicsList() {
    RegisterPhysics(new G4DecayPhysics());
    RegisterPhysics(new G4RadioactiveDecayPhysics());
    RegisterPhysics(new G4NeutronPhysics());
}

MyPhysicsList::~MyPhysicsList() {}
```

*Running the Simulation*
After setting up the above files, compile your application using CMake, and then run the generated executable. The neutron source will initiate the reaction with Thorium-232, and the physics processes will handle the subsequent interactions and decays.

This is a basic framework. You may need to extend it by adding specific models for the reactions and decays, visualizing the geometry, and collecting and analyzing the results.




---
# Footnotes
Codes are not updated with the changes made, these codes may or may not give desired results - if they even run.