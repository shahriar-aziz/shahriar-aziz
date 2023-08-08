#include<iostream>
#include<string>

class Vehicle
{
private:
std::string vehicleType;
std::string vehicleNumber;

public:
Vehicle(std::string type,std::string number)
:vehicleType(type), vehicleNumber(number){}
~Vehicle()
{
}

void displayDetails()
{
std::cout<<"Vehicle Type:"<<vehicleType<<std::endl;
std::cout<<"Vehicle Number:"<<vehicleNumber<<std::endl;
}
};
class Intermission
{
private:
float intermissionTime;
int route;
float penalty;
bool codeOfLawMaintenance;

public:
Intermission(float time,int r,float p,bool lawMaintenance):intermissionTime(time),route(r),penalty(p),codeOfLawMaintenance(lawMaintenance){}

void intermissionLap()
{
if(intermissionTime<5.0)
route=1;
else if(intermissionTime>5.0 && intermissionTime<10.0)
route=2;
else if(intermissionTime>=10.0)
route=3;
std::cout<<"Intermission Lap:"<<route<<std::endl;
}
};

class checkPost
{
private:
bool callOfficer;
float tollVehicle;

public:
checkPost(bool officer,float toll):callOfficer(officer),tollVehicle(toll){}
friend float callOfficer(checkPost& post,Vehicle& vehicle);
};

float callOfficer(checkPost& post,tollVehicle& toll)
{
float tollCollected=0.0;
float penaltyTaken=0.0;
if(post.callOfficer)
{
std::cout<<"Enter the toll amount for the vehicle(in dollars):";
std::cin>>post.tollVehicle;
tollCollected+=post.tollVehicle;
}
Intermission intermission(15.0,0,0.0,true);
intermission.intermissionLap();
if(intermission.route==1 && intermission.intermissionTime!=15)
{
penaltyTaken+=5.0;
}else if(intermission.route==2 && intermission.intermissionTime!=15)
{
penaltyTaken+=2.0;
}else if(intermission.route==3 && intermission.intermissionTime!=15)
{
penaltyTaken+=7.0;
}
std::cout<<"Toll Collected:"<<tollCollected<<" dollars"<<std::endl;
std::cout<<"Penalty taken:"<<penaltyTaken<<" dollars"<<std::endl;
return tollCollected;
}

int main()
{
Vehicle vehicle1("Car","ABC123");
Vehicle vehicle2("Truck","XYZ789");
std::cout<<"Vehicle 1 details:"<<std::endl;
vehicle1.displayDetails();
std::cout<<"Vehicle 2 details:"<<std::endl;
vehicle2.displayDetails();
Intermission intermission1(40.0,0,0.0,true);
intermission1.intermissionLap();
CheckPost post(true,0);
float collectedToll=callOfficer(post,vehicle1);
return 0;
}
