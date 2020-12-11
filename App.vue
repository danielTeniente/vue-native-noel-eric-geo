<template>
  <app-navigator></app-navigator>
</template>

<script>
import {
  createAppContainer,
  createMaterialTopTabNavigator,
  createStackNavigator
} from "vue-native-router";

import GeolocationScreen from "./screens/Geolocation.vue";
import DatabaseScreen from "./screens/Database.vue";

const Tabs = createMaterialTopTabNavigator({
  geolocalizacion: GeolocationScreen,
});

const StackNavigator = createStackNavigator(
  {
    Tabs,
    Camara: CameraScreen
  },
  {
    defaultNavigationOptions: {
      gestureEnabled: false,
      title: "Daniel Diaz implementacion",
      headerTitleStyle: {
        textAlign: "center",
        alignSelf: "center",
        color: "white"
      },
      headerStyle: {
        backgroundColor: "#088A85"
      }
    }
  }
);

const AppNavigator = createAppContainer(StackNavigator);

export default {
  components: { AppNavigator }
};
</script>
