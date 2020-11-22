CREATE TABLE [dbo].[FGTransaction](
[Seq] [bigint] IDENTITY(1,1) NOT NULL,
[Warehouse] [varchar](50) NOT NULL,
[ModelNo] [varchar](50) NOT NULL,
[SN] [varchar](50) NOT NULL,
[Quantity] [int] NOT NULL, --positive means in stock; negative means out of stock
[TrnTime] [datetime] NOT NULL, --transaction happening timestamp
CONSTRAINT [PK_FGTransaction_1] PRIMARY KEY CLUSTERED
(
[Seq] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY =
OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
SET ANSI_PADDING OFF
GO
ALTER TABLE [dbo].[FGTransaction] ADD CONSTRAINT [DF_FGTransaction_TrnTime]
DEFAULT (getdate()) FOR [TrnTime]
GO
