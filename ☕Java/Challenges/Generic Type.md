# Generic Type Challenge

Create a generic class to implement a league table for a sport. The class should allow teams to be added to the list, and store a list of teams that belong to the league. Your class should have a method to print out the teams in order, with the team at the top of the league printed first. Only teams of the same type should be added to any particular
instance of the league class - the program should fail to compile if an attempt is made to add an incompatible team.

```java
// 리그 클래스
public class League<T extends Team> {
    private String leagueName;
    private List<T> listOfTeams = new ArrayList<>();

    public League(String leagueName) {
        this.leagueName = leagueName;
    }

    public String getLeagueName() {
        return leagueName;
    }
    
    //리그에 팀을 더하는 메소드
    public boolean add(T team){
        if(listOfTeams.contains(team)){
            System.out.println(team.getTeamName() + " is already on the list.");
            return false;
        }else{
            listOfTeams.add(team);
            System.out.println(team.getTeamName() + " has been added." );
            return true;
        }
    }
    
    // 출력하는 메소드
    public void printTeams(){
        if(listOfTeams != null){
            String message  = "";
            for(T t : listOfTeams){
                message += t.getTeamName() + ", ";
            }
            System.out.println(this.leagueName + " has " + message);
        }else{
            System.out.println("No team is on the list yet.");
        }
    }
}

//팀 클래스 
public class Team {
    private String teamName;

    public Team(String teamName) {
        this.teamName = teamName;
    }

    public String getTeamName() {
        return teamName;
    }
}

// 팀 클래스를 상속받는 야구 팀 클래스
public class BaseballTeam extends Team {
    public BaseballTeam(String teamName) {
        super(teamName);
    }

    @Override
    public String getTeamName() {
        return super.getTeamName();
    }
}

// 팀 클래스를 상속받는 축구 팀 클래스
public class FootballTeam extends Team {
    public FootballTeam(String teamName) {
        super(teamName);
    }

    @Override
    public String getTeamName() {
        return super.getTeamName();
    }
}

// 메인 클래스
public class Main2 {
    public static void main(String[] args) {
        //축구 리그와 야구 리그 생성
        League<FootballTeam> premiereLeague = new League<>("Premiere League");
        League<BaseballTeam> majorLeague = new League<>("Major League");

        //축구 팀 생성
        FootballTeam manchesterUnited = new FootballTeam("Manchester United");
        FootballTeam barcelonaFC = new FootballTeam("Barcelona FC");
        FootballTeam pohangSteelers = new FootballTeam("Pohang Steelers");
        
        //야구 팀 생성
        BaseballTeam SFGiants = new BaseballTeam("SF Giants");
        BaseballTeam samsungLions = new BaseballTeam("Samsung Lions");
        BaseballTeam hanhwaEagles = new BaseballTeam("Hanhwa Eagles");
        
        //축구 리그에 축구 팀 더하고 출력, 야구 팀 더할 시 컴파일 에러 발생.
        premiereLeague.add(manchesterUnited); // Manchester United has been added.
        premiereLeague.add(barcelonaFC); // Barcelona FC has been added.
        premiereLeague.add(pohangSteelers); // Pohang Steelers has been added.
        premiereLeague.printTeams(); //Premiere League has Manchester United, Barcelona FC, Pohang Steelers, 

        //야구 리그에 야구 팀 더하고 출력, 축구 팀 더할 시 컴파일 에러 발생.
        majorLeague.add(SFGiants); // SF Giants has been added.
        majorLeague.add(samsungLions);  // Samsung Lions has been added.
        majorLeague.add(hanhwaEagles); // Hanhwa Eagles has been added.
        majorLeague.printTeams(); // Major League has SF Giants, Samsung Lions, Hanhwa Eagles,
    }
}
```

