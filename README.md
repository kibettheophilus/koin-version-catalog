# version-catalog

A [VersionCatalog](https://docs.gradle.org/current/userguide/version_catalogs.html) for the latest versions of **all** [Koin](https://github.com/InsertKoinIO/koin) dependencies

See the [TOML file](gradle/koin.versions.toml) for what is included

### Get Started

Add to your `settings.gradle.kts` file
```kotlin
dependencyResolutionManagement {
    repositories {
        mavenCentral()
    }

    versionCatalogs {
        create("koinLibs") {
            from("io.insert-koin:koin-version-catalog:4.1.0")
        }
    }
}
```

Use in your projects
```kotlin
dependencies {
    implementation(koinLibs.core)
    implementation(koinLibs.android)
    implementation(koinLibs.test)
    implementation(koinLibs.compose)
    implementation(koinLibs.ktor)
}
```