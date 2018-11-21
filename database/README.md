# Database

# Localized DB

Each service should have a localized, single DB. The DB may be loaded asynchronously via an importer / exporter service. All call to the APIs should be made against the localized DB.

# DB data load

Each service database should have a data loading mechanism. For development there must be some seed data or seeding mechanism available.

# DB migration strategy

Each service DB should have DB migration and capability to automatically update DB schema on deployment if needed.

# DB connection pooling

Service should use DB connection pooling for better performance.
