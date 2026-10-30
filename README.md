# Study Room Booking Tool

ASP.NET Core 10 MVC course project for finding free campus rooms and organizing study sessions.
Students can register, search available rooms, create course-linked sessions, and manage their own bookings.
Signed-in users can also manage the room and course catalogs.

## Run locally

Prerequisite: .NET 10 SDK. Node.js is not required. Bootstrap, Bootstrap Icons, and unobtrusive validation are loaded from public CDNs.

From the repository root (the folder containing `StudyRoomBooking.csproj`):

```bash
dotnet restore
dotnet run
```

Open the URL printed by the application (configured as `http://localhost:5080`). Select **Create account** to register. On first start, EF Core applies the migrations, creates `studyrooms-v2.db`, and seeds four rooms and three example courses. The previous `studyrooms.db` is preserved.

## Verify

```bash
dotnet build
dotnet test tests/StudyRoomBooking.Tests/StudyRoomBooking.Tests.csproj
```

## Project documentation

The full project report, including requirement traceability, architecture decisions, database design, security, tests, AI usage, and usability, is in [docs/PROJECT_DOCUMENTATION.md](docs/PROJECT_DOCUMENTATION.md).

## Known limitations

- The application is configured for local development; it has no public deployment URL.
- The GitHub repository is private, so examiners must be granted repository access or an approved public deployment must be added.
- Simultaneous booking requests are checked before saving but are not protected by a transaction or database-level exclusion constraint.
- Joining a session and posting messages are optional inspiration features and are not implemented.
