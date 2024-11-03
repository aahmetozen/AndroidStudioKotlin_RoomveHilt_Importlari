# AndroidStudioKotlin_RoomveHilt_Importlari
room ve hilt kutuphane importlari

build.gradle.kts(Project)

plugins{
alias(libs.plugins.ksp) apply false
alias(libs.plugins.hilt) apply false
}

----------------------------------------------------------------------

build.gradle.kts(Module)
plugins{
    alias(libs.plugins.ksp)
    alias(libs.plugins.hilt)
}

dependencies{
    // Hilt
    implementation(libs.dagger.hilt)
    ksp(libs.dagger.hilt.android.compiler)
    ksp(libs.dagger.hilt.compiler)
    implementation(libs.androidx.hilt.navigation.compose)

    // Room
    implementation(libs.room.runtime)
    implementation(libs.room.ktx)
    ksp(libs.room.compiler)

    // ViewModel
    implementation(libs.compose.lifecycle.viewmodel)
    implementation(libs.compose.lifecycle.runtime)


    implementation ("androidx.activity:activity-compose:1.7.2")
    implementation ("androidx.compose.ui:ui:1.4.2")
    implementation ("androidx.compose.material:material:1.4.2")
    implementation ("androidx.compose.ui:ui-tooling-preview:1.4.2")
    implementation ("androidx.lifecycle:lifecycle-viewmodel-compose:2.6.2")

}

----------------------------------------------------------------------

libs.versions.toml
[versions]
ksp = "1.9.10-1.0.13"
hilt = "2.48"
hilt-compiler = "1.2.0"
room = "2.6.1"
lifecycle-compose = "2.6.2"
appcompat = "1.7.0"

[libraries]
dagger-hilt = { module = "com.google.dagger:hilt-android", version.ref = "hilt" }
dagger-hilt-android-compiler = { module = "com.google.dagger:hilt-android-compiler", version.ref = "hilt" }
dagger-hilt-compiler = { module = "androidx.hilt:hilt-compiler", version.ref = "hilt-compiler" }
room-ktx = { module = "androidx.room:room-ktx", version.ref = "room" }
room-runtime = { module = "androidx.room:room-runtime", version.ref = "room" }
room-compiler = { module = "androidx.room:room-compiler", version.ref = "room" }
compose-lifecycle-viewmodel = { module = "androidx.lifecycle:lifecycle-viewmodel-compose", version.ref = "lifecycle-compose" }
compose-lifecycle-runtime = { module = "androidx.lifecycle:lifecycle-runtime-compose", version.ref = "lifecycle-compose" }
androidx-appcompat = { group = "androidx.appcompat", name = "appcompat", version.ref = "appcompat" }
androidx-hilt-navigation-compose = { module = "androidx.hilt:hilt-navigation-compose", version.ref = "hilt-compiler" }

[plugins]
ksp = { id = "com.google.devtools.ksp", version.ref = "ksp" }
hilt = { id = "com.google.dagger.hilt.android", version.ref = "hilt" }
