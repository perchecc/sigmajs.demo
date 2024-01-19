<script>
import cytoscape from "cytoscape";
export default {
  mounted() {
    var cy = cytoscape({
      container: document.getElementById("cy"), // container to render in

      elements: [
        // list of graph elements to start with
        {
          // node a
          data: { id: "a" },
        },
        {
          // node b
          data: { id: "b" },
        },
        {
          // node c
          data: { id: "c" },
        },
        {
          // node c
          data: { id: "d" },
        },
        {
          // node c
          data: { id: "e" },
        },
        // {
        //   // edge ab
        //   data: { id: "ab", source: "a", target: "b" },
        // },
        // {
        //   // edge ab
        //   data: { id: "bc", source: "b", target: "c" },
        // },
        // {
        //   // edge ab
        //   data: { id: "ca", source: "c", target: "a" },
        // },
        // {
        //   // edge ab
        //   data: { id: "ad", source: "a", target: "d" },
        // },
        // {
        //   // edge ab
        //   data: { id: "db", source: "d", target: "b" },
        // },
        // {
        //   // edge ab
        //   data: { id: "de", source: "d", target: "e" },
        // },
      ],

      style: [
        // the stylesheet for the graph
        {
          selector: "node",
          style: {
            "background-color": "#f00",
            label: "data(id)",
          },
        },

        {
          selector: "edge",
          style: {
            width: 3,
            "line-color": "#ccc",
            "target-arrow-color": "#ccc",
            "target-arrow-shape": "triangle",
            "curve-style": "bezier",
          },
        },
      ],

      layout: {
        name: "circle",
        // rows: 3,
        animate: false, // whether to transition the node positions
        animationDuration: 500, // duration of animation in ms if enabled
        padding: 100, // the padding on fit
      },
    });

    // var layout = cy.layout({
    //   name: "cose",
    //   animate: true, // whether to transition the node positions
    //   animationDuration: 500, // duration of animation in ms if enabled
    //   padding: 100, // the padding on fit
    // });

    // layout.run();

    cy.nodes().on("click", function (e) {
      const edges = cy.edges('[source = "a"]');

      var eles = cy.add([
        // { group: "nodes", data: { id: "n0" }, position: { x: 100, y: 100 } },
        // { group: "nodes", data: { id: "n1" }, position: { x: 200, y: 200 } },
        { group: "edges", data: { id: "ab", source: "a", target: "b" } },
        { group: "edges", data: { id: "bc", source: "b", target: "c" } },
        { group: "edges", data: { id: "ca", source: "c", target: "a" } },
        // {
        //   // edge ab
        //   data: { id: "ab", source: "a", target: "b" },
        // },
        // {
        //   // edge ab
        //   data: { id: "bc", source: "b", target: "c" },
        // },
        // {
        //   // edge ab
        //   data: { id: "ca", source: "c", target: "a" },
        // },
        // {
        //   // edge ab
        //   data: { id: "ad", source: "a", target: "d" },
        // },
        // {
        //   // edge ab
        //   data: { id: "db", source: "d", target: "b" },
        // },
        // {
        //   // edge ab
        //   data: { id: "de", source: "d", target: "e" },
        // },
      ]);
    });

    // // some time later...
    // setTimeout(function () {
    //   layout.stop();
    // }, 3000);
  },
};
</script>

<template>
  <div id="app">
    <!-- <header>
      <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

      <div class="wrapper">
        <HelloWorld msg="You did it!" />
      </div>
    </header>

    <main>
      <TheWelcome />
    </main> -->
    <div id="cy" style="width: 100%; height: 100%"></div>
  </div>
</template>

<style scoped>
#app {
  width: 100%;
  height: 100%;
}
</style>
