namespace Rpg;
class Program
{
    static void Main(string[] args)
    {
        DisplayMainUI();

    }
    static void DisplayMainUI()
    {
        Console.Clear();
        Console.WriteLine("스파르타 마을에 오신 여러분 환영합니다.");
        Console.WriteLine("이곳에서 던전으로 들어가기전 활동을 할 수 있습니다.");
        Console.WriteLine("");
        Console.WriteLine("1. 상태 보기");
        Console.WriteLine("2. 인벤토리");
        Console.WriteLine("3. 상점");
        Console.WriteLine("");
        Console.WriteLine("원하시는 행동을 입력해주세요.");

        int result;
        while (true)
        {
            string input = Console.ReadLine();
            bool isNumber = int.TryParse(input, out result);
            if (isNumber)
            {
                if (result >= 1 && result <= 3)
                    break;
            }
            Console.WriteLine("잘못된 입력입니다.");

        }
        switch (result)
        {
            case 1:
                DisplayMainUI();
                break;

            case 2:
                DisplayStatUI();
                break;

            case 3:
                DisplayShopUI();
                break;
        }
    }

    static void DisplayStatUI()
    {
        Console.Clear();
        Console.WriteLine("상태 보기");
        Console.WriteLine("캐릭터의 정보가 표시됩니다.");
        Console.WriteLine("");
        Console.WriteLine("0. 나가기");
        Console.WriteLine("원하시는 행동을 입력해주세요.");

        int result;
        while (true)
        {
            string input = Console.ReadLine();
            bool isNumber = int.TryParse(input, out result);
            if (isNumber)
            {
                if (result == 0)
                    break;
            }
            Console.WriteLine("잘못된 입력입니다.");
            switch (result)
            {
                case 0:
                    DisplayMainUI();
                    break;
            }
        }
        static void DisplayShopUI()
        {
            Console.Clear();
            Console.WriteLine("인벤토리");
            Console.WriteLine("보유 중인 아이템을 관리할 수 있습니다.");
            Console.WriteLine("");
            Console.WriteLine("[아이템 목록]");
            Console.WriteLine("");
            Console.WriteLine("1. 장착 관리");
            Console.WriteLine("0. 나가기");
            Console.WriteLine("");
            Console.WriteLine("원하시는 행동을 입력해주세요.");

            int result;
            while (true)
            {
                string input = Console.ReadLine();
                bool isNumber = int.TryParse(input, out result);
                if (isNumber)
                {
                    if (result >= 0 && result <= 1)
                        break;
                }
                Console.WriteLine("잘못된 입력입니다.");
                switch (result)
                {
                    case 0:
                        DisplayMainUI();
                        break;
                }
            }

        }
    }
}
