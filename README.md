# :zap: React, Chart.js를 이용한 템플릿.
:octocat: 바로가기 : https://light9639.github.io/React-Chart-js/ <br />

<img src="https://user-images.githubusercontent.com/95972251/192450218-c1c3c0c5-0871-40f8-86e5-aff7abc7b7e3.png" width="350px" /><br />

:sparkles: React, Chart.js를 이용한 템플릿 :sparkles:
## :tada: React로 만드는 Chart.js
 - CRA로 React 프로젝트 생성

    ```bash
    yarn create react-app my-app
    ```
    
 - Chart.js, React-chartjs-2 설치

    ```bash
    yarn add chart.js react-chartjs-2
    ```
## ✍️ Data.js 작성

 - Data.js 작성
 
    ```bash
    export const UserData = [
      {
        id: 1,
        year: 2016,
        userGain: 80000,
        userLost: 823,
      },
      {
        id: 2,
        year: 2017,
        userGain: 45677,
        userLost: 345,
      },
      {
        id: 3,
        year: 2018,
        userGain: 78888,
        userLost: 555,
      },
      {
        id: 4,
        year: 2019,
        userGain: 90000,
        userLost: 4555,
      },
      {
        id: 5,
        year: 2020,
        userGain: 4300,
        userLost: 234,
      },
    ];
    ```
## ✒️ App.js 작성
 - App.js 작성

    ```bash
    import { useState } from "react";
    import "./App.css";
    import BarChart from "./components/BarChart";
    import LineChart from "./components/LineChart";
    import PieChart from "./components/PieChart";
    import { UserData } from "./Data";

    function App() {
      const [userData, setUserData] = useState({
        labels: UserData.map((data) => data.year),
        datasets: [
          {
            label: "Users Gained",
            data: UserData.map((data) => data.userGain),
            backgroundColor: [
              'rgba(255, 99, 132, 0.2)',
              'rgba(54, 162, 235, 0.2)',
              'rgba(255, 206, 86, 0.2)',
              'rgba(75, 192, 192, 0.2)',
              'rgba(153, 102, 255, 0.2)',
              'rgba(255, 159, 64, 0.2)',
            ],
            borderColor: [
              'rgba(255, 99, 132, 1)',
              'rgba(54, 162, 235, 1)',
              'rgba(255, 206, 86, 1)',
              'rgba(75, 192, 192, 1)',
              'rgba(153, 102, 255, 1)',
              'rgba(255, 159, 64, 1)',
            ],
            borderWidth: 2,
          },
        ],
      });

      // IF YOU SEE THIS COMMENT: I HAVE GOOD EYESIGHT

      return (
        <div className="App">
          <div style={{ width: 700 }}>
            <BarChart chartData={userData} />
          </div>
          <div style={{ width: 700 }}>
            <LineChart chartData={userData} />
          </div>
          <div style={{ width: 700 }}>
            <PieChart chartData={userData} />
          </div>
        </div>
      );
    }

    export default App;
    ```

## 📝 BarChart.js, LineChart.js, PieChart.js 작성
 - components 폴더 생성.
 
 - BarChart.js 작성

    ```bash
    import React from "react";
    import { Bar } from "react-chartjs-2";
    import { Chart as ChartJS } from "chart.js/auto";

    function BarChart({ chartData }) {
      return <Bar data={chartData} />;
    }

    export default BarChart;
    ```
 - LineChart.js 작성
 
      ```bash
      import React from "react";
      import { Line } from "react-chartjs-2";
      import { Chart as ChartJS } from "chart.js/auto";

      function LineChart({ chartData }) {
        return <Line data={chartData} />;
      }

      export default LineChart;
      ```
 - PieChart.js 작성
 
    ```bash
    import React from "react";
    import { Pie } from "react-chartjs-2";
    import { Chart as ChartJS } from "chart.js/auto";

    function PieChart({ chartData }) {
      return <Pie data={chartData} />;
    }

    export default PieChart;
    ```
## :rocket: 실행및 빌드 방법
 - 실행 명령어
    ```bash
    yarn start
    ```

 - 빌드 명령어
    ```bash
    yarn build
    ```
## **:paperclip: 출처**
- 출처1 : <a href="https://velog.io/@ksh4820/react-chartjs-2-%EA%B7%B8%EB%9E%98%ED%94%84">https://velog.io/@ksh4820/react-chartjs-2-%EA%B7%B8%EB%9E%98%ED%94%84</a>
- 출처2 : <a href="https://byul91oh.tistory.com/541">https://byul91oh.tistory.com/541</a>
- 출처3 : <a href="https://react-chartjs-2.js.org/">https://react-chartjs-2.js.org/</a>
