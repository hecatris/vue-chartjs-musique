<script>
import { Bar } from "vue-chartjs";
import { ecoutes, ecoutesLegale } from "../utils";
export default {
  extends: Bar,
  mounted() {
    this.renderChart(
      {
        labels: Object.keys(ecoutes()),
        datasets: [
          {
            label: "styles écoutés",
            backgroundColor: "#f87979",
            data: Object.values(ecoutes()),
            stack: "Stack 0",
          },
          {
            label: "écoute uniquement légale",
            backgroundColor: "#76ed3b",
            data: Object.values(ecoutesLegale(1)),
            stack: "Stack 1",
          },
          {
            label: "écoute parfois de manière illégale",
            backgroundColor: "#edea3b",
            data: Object.values(ecoutesLegale(2)),
            stack: "Stack 1",
          },
          {
            label: "écoute autant légale qu'illégale",
            backgroundColor: "#ed793b",
            data: Object.values(ecoutesLegale(3)),
            stack: "Stack 1",
          },
          {
            label: "écoute uniquement illégale",
            backgroundColor: "#ed653b",
            data: Object.values(ecoutesLegale(4)),
            stack: "Stack 1",
          },
        ],
      },
      { responsive: true, maintainAspectRatio: false }
    );
  },
};
</script>
